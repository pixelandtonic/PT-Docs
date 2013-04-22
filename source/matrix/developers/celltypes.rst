Celltype Development
====================

Developing a celltype for Matrix is just as easy as creating a `fieldtype <http://ellislab.com/expressionengine/user-guide/development/fieldtypes.html>`_ in EE. In fact, the first step is to create one.

The only function required to get your fieldtype to show up as a Matrix celltype is `display_cell() <#display_cell>`_.

Celltype Functions
------------------

Here are all of the Matrix-specific functions you can add:

``display_cell_settings( $data )``
    Adds custom cell settings to the Matrix Configuration setting within the Edit Field form.

    **Arguments**

    ``$data``
        An array of the previously-saved celltype settings for the current column.

    **Returns**

    A multidimensional array of setting name/HTML pairs.

    .. code-block:: php

        <?php

        class My_celltype_ft
        {
            // ...

            function display_cell_settings( $data )
            {
                if (! isset($data['maxl']))
                {
                    $data['maxl'] = '';
                }

                if (! isset($data['multiline']))
                {
                    $data['multiline'] = 'n';
                }

                return array(
                    array(lang('maxl'), form_input('maxl', $data['maxl'], 'class="matrix-textarea"')),
                    array(lang('multiline'), form_checkbox('multiline', 'y', ($data['multiline'] == 'y')))
                );
            }

            // ...
        }

``save_cell_settings( $data )``
    Modifies the Matrix cell settings’ post data before it gets saved to the database.

    **Arguments**

    ``$data``
        Post data that came from any inputs you created in ``display_cell_settings()``.

    **Returns**

    An array with the modified post data.

    .. code-block:: php

        <?php

        class My_celltype_ft
        {
            // ...

            function save_cell_settings( $data )
            {
                if (! is_numeric($data['maxl']))
                {
                    $data['maxl'] = 0;
                }

                return $data;
            }

            // ...
        }

``settings_modify_matrix_column( $data )``
    Modifies the settings of your exp_matrix_data column(s).

    **Arguments**

    ``$data``
        The data about your column that was inserted into exp_matrix_cols, as well as a “matrix_action” key that describes what Matrix is about to do to it (“add”, “get_data”, or “delete”).

    **Returns**

    Array with the settings for your exp_matrix_data columns, which will be passed to dbforge->add_column() upon creation, and dbforge->modify_column() when changed.

    .. code-block:: php

        <?php

        class My_celltype_ft
        {
            // ...

            function settings_modify_matrix_column($data)
            {
                // decode the col settings
                $settings = unserialize(base64_decode($data['col_settings']));

                switch ($settings['content'])
                {
                    case 'integer':
                    {
                        return array('col_id_'.$data['col_id'] => array('type' => 'int', 'default' => 0));
                    }

                    case 'numeric':
                    {
                        return array('col_id_'.$data['col_id'] => array('type' => 'float', 'default' => 0));
                    }
                }
            }

            // ...
        }

``display_cell( $data )``
    Creates the custom Matrix cell HTML for the Publish form.

    **Arguments**

    ``$data``
        The previously-saved cell data.

    **Other Variables**

    ``$this->settings``
        Combination of your fieldtype’s global settings and the column settings.

    ``$this->field_id``
        The Matrix field’s field_id.

    ``$this->field_name``
        The Matrix field’s field_name, e.g. “field_id_1”.

    ``$this->row_id``
        The row’s row_id.

    ``$this->col_id``
        The column’s col_id.

    ``$this->cell_name``
        The name you give your cell input.

    **Return**

    String of HTML to be inserted into the Matrix cell in the Publish form

    .. code-block:: php

        <?php

        class My_celltype_ft
        {
            // ...

            function display_cell( $data )
            {
                return '<textarea class="matrix-textarea" name="'.$this->cell_name.'" rows="1">'.$data.'</textarea>';
            }

            // ...
        }

``validate_cell( $data )``
    Validates the Matrix cell’s post data before it gets saved to the database.

    **Arguments**

    ``$data``
        The cell’s post data.

    **Other Variables**

    ``$this->settings``
        Combination of your fieldtype’s global settings, the column settings, and the variables “col_id”, “col_name”, “col_required”, and “row_name”.

    **Return**

    Either the validation error, or ``TRUE`` if there isn’t an error.

    .. code-block:: php

        <?php

        class My_celltype_ft
        {
            // ...

            function validate_cell( $data )
            {
                if ($this->settings['col_required'] == 'y')
                {
                    if (! $data)
                    {
                        return lang('col_required');
                    }
                }

                return TRUE;
            }

            // ...
        }

``save_cell( $data )``
    Modifies the Matrix cell’s post data before it gets saved to the database.

    **Arguments**

    ``$data``
        The cell’s post data.

    **Other Variables**

    ``$this->settings``
        Combination of your fieldtype’s global settings, the column settings, and the variables “col_id”, “col_name”, “col_required”, and “row_name”.

    **Returns**

    The modified post data

    .. code-block:: php

        <?php

        class My_celltype_ft
        {
            // ...

            function save_cell( $data )
            {
                if ($data == '&nbsp;')
                {
                    $data = '';
                }

                return $data;
            }

            // ...
        }

``post_save_cell( $data )``
    Performs actions after a row has been saved.

    **Arguments**

    ``$data``
        The cell’s post data, or the data returned by save_cell()

    **Other Variables**

    ``$this->settings``
        Combination of your fieldtype’s global settings, the column settings, the col_id, col_name, row_id, and row_name

``delete_rows( $row_ids )``
    Performs actions right before rows get deleted.

    **Arguments**

    ``$row_ids``
        The row IDs about to be deleted.
