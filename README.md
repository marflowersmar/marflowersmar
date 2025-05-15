flowchart LR
    %% Bloques principales
    K[Teclado Matricial]
    D[DIV<br/>CLK → scan_clk]
    S[SCAN<br/>scan_clk → numero,<br/>fila]
    M[MEM<br/>scan_clk & numero →<br/>memoria, LEDO]
    SEL[SEL<br/>memoria & sel →<br/>mostrar_num]
    DISP[DISP<br/>mostrar_num →<br/>anDisp, Seg]

    %% Entradas
    CLK([CLK]) --> D
    D --> S
    K -->|Columna| S
    S -->|Fila| K

    %% Flujo de datos
    S --> M
    M -->|LED0| LEDO_out([LEDO])
    M --> SEL
    sel([sel]) --> SEL
    SEL --> DISP
    DISP --> out([anDisp, Seg])

