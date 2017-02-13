# aliases.json
aliases.json for hopglass-server

![Bild1](https://raw.githubusercontent.com/freifunk-fulda/aliases.json/master/forcegraph.png "Übersicht der Gateway's in Fulda")

## Werte für Fulda

### MAC - Adresses (Other-Interface)
(Zum herstellen des virtuellen Mesh.)

#### Gateway 1

-- Tunnel 1

    da:00:8e:72:da:a1 
-- Tunnel 2

    da:00:8e:72:da:a2 

#### Gateway 2

-- Tunnel 1

     26:13:9d:ea:e1:e1
-- Tunnel 2

    26:13:9d:ea:e1:e2 

#### Gateway 4

-- Tunnel 1

    26:13:9d:da:31:01 
    
-- Tunnel 2

    26:13:9d:da:31:02 

## Allgemeine Erläuterung
### Uplink (Statistiken->Nodes an Gateway)

##### Beispiel Gateway 1 Uplink:
    
    "deadbeef0201": {
        "firstseen": "2015-09-25T00:45:02",
        "nodeinfo": {
            "hostname": "Gateway-1",
            "node_id": "de:ad:be:ef:04:01",
            "network": {
                "mac": "de:ad:be:ef:04:01"
            }
        }
    },
    
##### Beispiel Gateway 1 (Tunnel 1)

       "dae78e72daa1": {
            "nodeinfo": {
                "owner": {
                "contact": "Freifunk Fulda"
                },
    "no": {
                "location": {
                "longitude": 11.013692021,
                "latitude": 49.449364830
            }},
            "hostname": "Gateway-1-Tunnel-1",
            "network": {
                "addresses": [
                    "10.185.0.1"
                ],
                "mac": "da:e7:8e:72:da:a1",
                "mesh": {
                    "bat0": {
                        "interfaces": {
                            "other": [
                                "da:00:8e:72:da:a1"
                            ],
                            "tunnel": [
                                "da:e7:8e:72:da:a1"
                            ]
                        }
                    }
                },
                "mesh_interfaces": [
                    "da:00:8e:72:da:a1",
                    "da:e7:8e:72:da:a1 "
                ]
            },
            "node_id": "dae78e72daa1",
            "hardware": {
                "model": "Common KVM processor @ 2.26GHz",
                "nproc": "2"
            },
            "pages": [
                "http://gw01.fulda.freifunk.net/"
            ]
        },
        "flags": {
            "gateway": true
        },
        "firstseen": "2015-09-25T00:45:02",
        "statistics": {
            "clients": {
                "wifi": 0,
                "total": 0
            }
        },
        "neighbours": {
            "batadv": {
                "da:e7:8e:72:da:a1": {},
                "da:00:8e:72:da:a1": {
                    "neighbours": {
                        "26:13:9d:ea:e1:e1": { "lastseen": 0.08, "tq": 255 },
                        "da:00:8e:72:da:a2": { "lastseen": 0.08, "tq": 255 }
                    }
                }
            }
        }
    },  
    
#### Koordinaten des Gateway setzen
(In diesem Fall auskommentiert)  

    "no": {
                "location": {
                "longitude": 11.013692021,
                "latitude": 49.449364830
            }},

zum setzen der Koordinaten:

				},
                "location": {
                "longitude": 11.013692021,
                "latitude": 49.449364830
            },
            
#### benennen des Gateways
(In diesem Fall gibt es 2 Fastd-Instanzen pro Gateway.)

    "hostname": "Gateway-1-Tunnel-1",
    
#### IP-Adresse des Gateways

    "addresses": [
                     "10.185.0.1"
                 ],

#### MAC-Adresse des Gateways

     "mac": "da:e7:8e:72:da:a1",


#### Das (virtuelle) Mesh + VPN zu den Knoten

    "mesh": {
                "bat0": {

Das "other"-Interface wird für das virtuelle Mesh verwendet:

                    "interfaces": {
                        "other": [
                            "da:00:8e:72:da:a1"
                        ],
Der "tunnel"-Eintrag steht für die MAC-Adresse des VPN:

                        "tunnel": [
                            "da:e7:8e:72:da:a1"
                        ]
                    }
                }
            },

#### Man trägt beide Interfaces als Mesh-Interface ein:

    "mesh_interfaces": [
                           "da:00:8e:72:da:a1",
                           "da:e7:8e:72:da:a1 "
                       ]


