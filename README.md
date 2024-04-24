<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
<body>
    <h1 style="text-align: center;">ChampSim</h1>
    <p style="text-align: center;">ChampSim is a trace-based simulator for microarchitecture studies. Sign up for the public mailing list by sending an empty email to <a href="mailto:champsim+subscribe@googlegroups.com">champsim+subscribe@googlegroups.com</a>.</p>
    <p style="text-align: center;">Traces for the 3rd Data Prefetching Championship (DPC-3) can be found <a href="https://dpc3.compas.cs.stonybrook.edu/?SW_IS">here</a>. A set of traces used for the 2nd Cache Replacement Championship (CRC-2) can be found <a href="http://bit.ly/2t2nkUj">here</a>.</p>
    <h2 style="text-align: center;">Setup Instructions</h2>
    <ol>
        <li>Desktop should have Linux operating system. It can be installed using VirtualBox <a href="https://www.virtualbox.org/wiki/Linux_Downloads">here</a>.</li>
        <li>Open terminal using CTRL+ALT+T.</li>
        <li>Run command: <code>sudo apt-get install curl zip unzip tar</code>.</li>
        <li>Make a new folder named ChampSim and navigate into the folder using: <code>cd ChampSim/</code>.</li>
        <li>Download ChampSim repository from <a href="https://github.com/0xd3ba/ChampSim">here</a> into the ChampSim folder.</li>
        <li>Extract the ChampSim file using the command: <code>unzip</code>.</li>
    </ol>
    <h2 style="text-align: center;">Download DPC-3 Trace</h2>
    <p style="text-align: center;">Professor Daniel Jimenez at Texas A&M University kindly provided traces for DPC-3. Use the following script to download these traces (~20GB size and max simpoint only).</p>
    <pre style="text-align: center;">
        $ cd scripts
        $ ./download_dpc3_traces.sh
    </pre>
    <h2 style="text-align: center;">Run Simulation</h2>
    <p style="text-align: center;">Execute run_champsim.sh with proper input arguments.</p>
    <pre style="text-align: center;">
        Usage: ./run_champsim.sh [BINARY] [N_WARM] [N_SIM] [TRACE] [OPTION]
        $ ./run_champsim.sh bimodal-no-no-no-no-lru-1core 1 10 400.perlbench-41B.champsimtrace.xz
    </pre>
    <h2 style="text-align: center;">How to Create Traces</h2>
    <p style="text-align: center;">We have included only 4 sample traces, taken from SPEC CPU 2006. These traces are short (10 million instructions) and do not necessarily cover the range of behaviors your replacement algorithm will likely see in the full competition trace list (not included). We STRONGLY recommend creating your own traces, covering a wide variety of program types and behaviors.</p>
    <p style="text-align: center;">The included Pin Tool champsim_tracer.cpp can be used to generate new traces. We used Pin 3.2 (pin-3.2-81205-gcc-linux), and it may require installing libdwarf.so, libelf.so, or other libraries if you do not already have them. Please refer to the Pin documentation <a href="https://software.intel.com/sites/landingpage/pintool/docs/81205/Pin/html/">here</a> for working with Pin 3.2.</p>
    <h2 style="text-align: center;">Evaluate Simulation</h2>
    <p style="text-align: center;">ChampSim measures the IPC (Instruction Per Cycle) value as a performance metric. There are some other useful metrics printed out at the end of simulation.</p>
    <p style="text-align: center;">Good luck and be a champion!</p>
</body>
</html>
