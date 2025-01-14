================================================
insbuf - insert buffer cells for connected wires
================================================

.. raw:: latex

    \begin{comment}

:code:`yosys> help insbuf`
--------------------------------------------------------------------------------

.. container:: cmdref


    .. code:: yoscrypt

        insbuf [options] [selection]

    ::

        Insert buffer cells into the design for directly connected wires.


    .. code:: yoscrypt

        -buf <celltype> <in-portname> <out-portname>

    ::

            Use the given cell type instead of $_BUF_. (Notice that the next
            call to "clean" will remove all $_BUF_ in the design.)

.. raw:: latex

    \end{comment}

.. only:: latex

    ::

        
            insbuf [options] [selection]
        
        Insert buffer cells into the design for directly connected wires.
        
            -buf <celltype> <in-portname> <out-portname>
                Use the given cell type instead of $_BUF_. (Notice that the next
                call to "clean" will remove all $_BUF_ in the design.)
        
