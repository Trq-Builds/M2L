```mermaid
graph LR
    subgraph Internet
        WAN[WAN 172.16.0.0/16]
    end

    WAN -- DHCP_Interface_out --> FW[Stormshield]

    subgraph DMZ_Zone
        FW -- IP_Statique_192.168.0.0/24 --> DMZ[Serveurs DMZ]
    end

    FW -- 172.18.0.0/16 --> R1[Routeur Cisco]
    
    R1 -- 172.17.0.0/16 --> SW[Switch L3]

    subgraph LAN
        SW --- Clients
        SW --- Imprimantes
    end

    style WAN fill:#f9f,stroke:#333
    style FW fill:#f66,stroke:#333
    style R1 fill:#69f,stroke:#333
    style SW fill:#9f9,stroke:#333
    ```
    
