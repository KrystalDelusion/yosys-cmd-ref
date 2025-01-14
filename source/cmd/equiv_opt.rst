===================================================
equiv_opt - prove equivalence for optimized circuit
===================================================

.. raw:: latex

    \begin{comment}

:code:`yosys> help equiv_opt`
--------------------------------------------------------------------------------

.. container:: cmdref


    .. code:: yoscrypt

        equiv_opt [options] [command]

    ::

        This command uses temporal induction to check circuit equivalence before and
        after an optimization pass.


    .. code:: yoscrypt

        -run <from_label>:<to_label>

    ::

            only run the commands between the labels (see below). an empty
            from label is synonymous to the start of the command list, and empty to
            label is synonymous to the end of the command list.


    .. code:: yoscrypt

        -map <filename>

    ::

            expand the modules in this file before proving equivalence. this is
            useful for handling architecture-specific primitives.


    .. code:: yoscrypt

        -blacklist <file>

    ::

            Do not match cells or signals that match the names in the file
            (passed to equiv_make).


    .. code:: yoscrypt

        -assert

    ::

            produce an error if the circuits are not equivalent.


    .. code:: yoscrypt

        -multiclock

    ::

            run clk2fflogic before equivalence checking.


    .. code:: yoscrypt

        -async2sync

    ::

            run async2sync before equivalence checking.


    .. code:: yoscrypt

        -undef

    ::

            enable modelling of undef states during equiv_induct.


    ::

        The following commands are executed by this verification command:

            run_pass:
                hierarchy -auto-top
                design -save preopt
                [command]
                design -stash postopt

            prepare:
                design -copy-from preopt  -as gold A:top
                design -copy-from postopt -as gate A:top

            techmap:    (only with -map)
                techmap -wb -D EQUIV -autoproc -map <filename> ...

            prove:
                clk2fflogic    (only with -multiclock)
                async2sync     (only with -async2sync)
                equiv_make -blacklist <filename> ... gold gate equiv
                equiv_induct [-undef] equiv
                equiv_status [-assert] equiv

            restore:
                design -load preopt

.. raw:: latex

    \end{comment}

.. only:: latex

    ::

        
            equiv_opt [options] [command]
        
        This command uses temporal induction to check circuit equivalence before and
        after an optimization pass.
        
            -run <from_label>:<to_label>
                only run the commands between the labels (see below). an empty
                from label is synonymous to the start of the command list, and empty to
                label is synonymous to the end of the command list.
        
            -map <filename>
                expand the modules in this file before proving equivalence. this is
                useful for handling architecture-specific primitives.
        
            -blacklist <file>
                Do not match cells or signals that match the names in the file
                (passed to equiv_make).
        
            -assert
                produce an error if the circuits are not equivalent.
        
            -multiclock
                run clk2fflogic before equivalence checking.
        
            -async2sync
                run async2sync before equivalence checking.
        
            -undef
                enable modelling of undef states during equiv_induct.
        
        The following commands are executed by this verification command:
        
            run_pass:
                hierarchy -auto-top
                design -save preopt
                [command]
                design -stash postopt
        
            prepare:
                design -copy-from preopt  -as gold A:top
                design -copy-from postopt -as gate A:top
        
            techmap:    (only with -map)
                techmap -wb -D EQUIV -autoproc -map <filename> ...
        
            prove:
                clk2fflogic    (only with -multiclock)
                async2sync     (only with -async2sync)
                equiv_make -blacklist <filename> ... gold gate equiv
                equiv_induct [-undef] equiv
                equiv_status [-assert] equiv
        
            restore:
                design -load preopt
        
