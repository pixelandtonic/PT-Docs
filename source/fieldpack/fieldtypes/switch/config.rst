Configuration
=============

Switch fields have five settings:

OFF Label
    The label of the “OFF” (left) position of the switch in the CP.

OFF Value
    The value of the field when it is switched off (to the left).

    **Note:** Leave this setting blank if you want to be able to use your field in simple template conditionals:

    .. code-block:: html

        {if my_pill_field}
            <p>Hot!<p>
        {if:else}
            <p>Not hot.</p>
        {/if}

    Otherwise you will need to be checking for the specific ON/OFF value:

    .. code-block:: html

        {if my_pill_field == "hot"}
            <p>Hot!<p>
        {if:else}
            <p>Not hot.</p>
        {/if}

ON Label
    The label of the “ON” (right) position of the switch in the CP.

ON Value
    The value of the field when it is switched on (to the right).

Default Position
    The default position of the field for new entries (OFF or ON).
