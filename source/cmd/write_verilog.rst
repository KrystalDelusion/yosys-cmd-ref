============================================
write_verilog - write design to Verilog file
============================================

.. raw:: latex

    \begin{comment}

:code:`yosys> help write_verilog`
--------------------------------------------------------------------------------

.. container:: cmdref


    .. code:: yoscrypt

        write_verilog [options] [filename]

    ::

        Write the current design to a Verilog file.


    .. code:: yoscrypt

        -sv

    ::

            with this option, SystemVerilog constructs like always_comb are used


    .. code:: yoscrypt

        -norename

    ::

            without this option all internal object names (the ones with a dollar
            instead of a backslash prefix) are changed to short names in the
            format '_<number>_'.


    .. code:: yoscrypt

        -renameprefix <prefix>

    ::

            insert this prefix in front of auto-generated instance names


    .. code:: yoscrypt

        -noattr

    ::

            with this option no attributes are included in the output


    .. code:: yoscrypt

        -attr2comment

    ::

            with this option attributes are included as comments in the output


    .. code:: yoscrypt

        -noexpr

    ::

            without this option all internal cells are converted to Verilog
            expressions.


    .. code:: yoscrypt

        -siminit

    ::

            add initial statements with hierarchical refs to initialize FFs when
            in -noexpr mode.


    .. code:: yoscrypt

        -nodec

    ::

            32-bit constant values are by default dumped as decimal numbers,
            not bit pattern. This option deactivates this feature and instead
            will write out all constants in binary.


    .. code:: yoscrypt

        -decimal

    ::

            dump 32-bit constants in decimal and without size and radix


    .. code:: yoscrypt

        -nohex

    ::

            constant values that are compatible with hex output are usually
            dumped as hex values. This option deactivates this feature and
            instead will write out all constants in binary.


    .. code:: yoscrypt

        -nostr

    ::

            Parameters and attributes that are specified as strings in the
            original input will be output as strings by this back-end. This
            deactivates this feature and instead will write string constants
            as binary numbers.


    .. code:: yoscrypt

        -simple-lhs

    ::

            Connection assignments with simple left hand side without
            concatenations.


    .. code:: yoscrypt

        -extmem

    ::

            instead of initializing memories using assignments to individual
            elements, use the '$readmemh' function to read initialization data
            from a file. This data is written to a file named by appending
            a sequential index to the Verilog filename and replacing the extension
            with '.mem', e.g. 'write_verilog -extmem foo.v' writes 'foo-1.mem',
            'foo-2.mem' and so on.


    .. code:: yoscrypt

        -defparam

    ::

            use 'defparam' statements instead of the Verilog-2001 syntax for
            cell parameters.


    .. code:: yoscrypt

        -blackboxes

    ::

            usually modules with the 'blackbox' attribute are ignored. with
            this option set only the modules with the 'blackbox' attribute
            are written to the output file.


    .. code:: yoscrypt

        -selected

    ::

            only write selected modules. modules must be selected entirely or
            not at all.


    .. code:: yoscrypt

        -v

    ::

            verbose output (print new names of all renamed wires and cells)


    ::

        Note that RTLIL processes can't always be mapped directly to Verilog
        always blocks. This frontend should only be used to export an RTLIL
        netlist, i.e. after the "proc" pass has been used to convert all
        processes to logic networks and registers. A warning is generated when
        this command is called on a design with RTLIL processes.

.. raw:: latex

    \end{comment}

.. only:: latex

    ::

        
            write_verilog [options] [filename]
        
        Write the current design to a Verilog file.
        
            -sv
                with this option, SystemVerilog constructs like always_comb are used
        
            -norename
                without this option all internal object names (the ones with a dollar
                instead of a backslash prefix) are changed to short names in the
                format '_<number>_'.
        
            -renameprefix <prefix>
                insert this prefix in front of auto-generated instance names
        
            -noattr
                with this option no attributes are included in the output
        
            -attr2comment
                with this option attributes are included as comments in the output
        
            -noexpr
                without this option all internal cells are converted to Verilog
                expressions.
        
            -siminit
                add initial statements with hierarchical refs to initialize FFs when
                in -noexpr mode.
        
            -nodec
                32-bit constant values are by default dumped as decimal numbers,
                not bit pattern. This option deactivates this feature and instead
                will write out all constants in binary.
        
            -decimal
                dump 32-bit constants in decimal and without size and radix
        
            -nohex
                constant values that are compatible with hex output are usually
                dumped as hex values. This option deactivates this feature and
                instead will write out all constants in binary.
        
            -nostr
                Parameters and attributes that are specified as strings in the
                original input will be output as strings by this back-end. This
                deactivates this feature and instead will write string constants
                as binary numbers.
        
            -simple-lhs
                Connection assignments with simple left hand side without
                concatenations.
        
            -extmem
                instead of initializing memories using assignments to individual
                elements, use the '$readmemh' function to read initialization data
                from a file. This data is written to a file named by appending
                a sequential index to the Verilog filename and replacing the extension
                with '.mem', e.g. 'write_verilog -extmem foo.v' writes 'foo-1.mem',
                'foo-2.mem' and so on.
        
            -defparam
                use 'defparam' statements instead of the Verilog-2001 syntax for
                cell parameters.
        
            -blackboxes
                usually modules with the 'blackbox' attribute are ignored. with
                this option set only the modules with the 'blackbox' attribute
                are written to the output file.
        
            -selected
                only write selected modules. modules must be selected entirely or
                not at all.
        
            -v
                verbose output (print new names of all renamed wires and cells)
        
        Note that RTLIL processes can't always be mapped directly to Verilog
        always blocks. This frontend should only be used to export an RTLIL
        netlist, i.e. after the "proc" pass has been used to convert all
        processes to logic networks and registers. A warning is generated when
        this command is called on a design with RTLIL processes.
        
