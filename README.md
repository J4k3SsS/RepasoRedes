# Laboratorio CLI CNOC

Consola simulada (Huawei VRP, Cisco IOS y FortiGate) para practicar el diagnóstico del N1 desde el teléfono o la PC.
Todos los equipos, IP, clientes y salidas son **ficticios**.

## Juego de repaso (repaso.html)

Quiz, tarjetas y ordenar pasos con 288 preguntas por tema (OSI, TCP/IP, VLAN, QinQ, rutas, última milla, UTP, comandos, OSPF B1-B3, BGP B1-B3, RR B1-B2 y filtros). Se abre desde la consola o directo en `/repaso.html`.

## Práctica libre

Cinco equipos con una red sana (2 Huawei, 2 Cisco y 1 FortiGate). Escribes un comando y te devuelve la salida y, en azul, **para qué sirve, qué mirar y su equivalente** en la otra marca. También explica los filtros, el ping y los comandos de configuración (que siguen bloqueados).

## Casos incluidos

| # | Caso | Tema |
|---|---|---|
| 1 | PE-SUR-01 no llega a Full | OSPF (ExStart / MTU) |
| 2 | Desapareció PE-NOR-01 | OSPF (Hello/Dead) |
| 3 | El FortiGate quedó en INIT | OSPF (un solo sentido) |
| 4 | SUR va lento en hora pico | OSPF (costo) |
| 5 | Cliente nuevo sin servicio | VLAN no permitida |
| 6 | Cliente lento, sin caídas | Duplex mismatch |
| 7 | Microcortes en fibra | Potencia óptica |
| 8 | «El CPE no responde» | VRF / VPN-instance |
| 9 | «Las páginas cargan a medias» | MTU del camino |
| 10 | PE-NOR-02 no sube tras cambiar el radio | OSPF (MTU en medio, QinQ) |
| 11 | El hotel no navega tras cambiar su router | BGP (Bad peer AS) |
| 12 | Desde Internet no llegan al hotel | Filtros de rutas (prefix-list) |

## Cómo publicarlo en GitHub Pages

1. Entra a github.com y crea un repositorio nuevo (por ejemplo `lab-cli-cnoc`), público.
2. Toca **Add file → Upload files** y sube `index.html`, `repaso.html` y este `README.md`.
3. Ve a **Settings → Pages**.
4. En **Source** elige **Deploy from a branch**, rama `main`, carpeta `/ (root)`, y guarda.
5. En 1 o 2 minutos queda en: `https://TU-USUARIO.github.io/lab-cli-cnoc/`

Para actualizarlo, sube de nuevo `index.html` (reemplaza el anterior).

## Uso

- Abreviaturas: `dis ospf peer br`, `sh ip ospf nei`, `dis int g0/0/3`.
- `?` muestra los comandos disponibles; **Tab** completa; ↑ repite.
- Filtros: `| include`, `| exclude`, `| begin` (Cisco también `| section`; FortiGate `| grep`).
- Ping simulado: Huawei `ping -s 1472 -f [-vpn-instance NOMBRE] <ip>`, Cisco `ping [vrf NOMBRE] <ip> size 1500 df-bit`.
- Los comandos de configuración están bloqueados (N1 = solo lectura).
- El progreso se guarda solo en el navegador.

> No agregues datos reales de clientes, IP o configuraciones de la empresa: el repositorio es público.
