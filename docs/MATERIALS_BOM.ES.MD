# 📦 Lista de Materiales y Herramientas (BOM)
> **Proyecto:** Sistema automatizado de gestión, procesado de materiales y control de calidad industrial  
> **Plataforma:** Siemens S7-1200 / PROFINET / TIA Portal  

---

## 🛠️ 1. Herramientas y equipamiento de taller

### 🔧 1.1 Herramientas de montaje mecánico
* **Juego de llaves Allen (hexagonales):** $2.5\text{ mm}$, $3\text{ mm}$, $4\text{ mm}$ y $5\text{ mm}$ (para tornillos M3, M4 y M5).
* **Llaves fijas / de vaso:** $7\text{ mm}$, $8\text{ mm}$ y $10\text{ mm}$ (para tuercas de perfilería y célula de carga).
* **Destornilladores de precisión:** planos y de estrella (Phillips).
* **Calibrador / pie de rey:** para verificación de dimensiones de probetas y alineación de guías.
* **Escuadra de taller o nivel de burbuja:** para el escuadrado del pórtico a $90^\circ$.
* **Cúter y tijeras:** para ajuste de tubos de protección y cinta transportadora.

### ⚡ 1.2 Herramientas eléctricas y cableado
* **Destornilladores aislados de electricista (VDE):** planos ($2-3\text{ mm}$) para clemas de PLC y estrella (PH1/PH2) para fuente y driver.
* **Alicate pelacables automático:** para mangueras de $0.25\text{ mm}^2$ (señal) a $1.5\text{ mm}^2$ (potencia).
* **Crimpadora de punteras terminales:** para punteras huecas aisladas de $0.5\text{ mm}^2$ a $1.5\text{ mm}^2$.
* **Alicate de corte diagonal:** para corte de cableado y bridas.
* **Estación de soldadura de estaño:** para empalmes de sensores y prolongaciones.
* **Tubo termorretráctil:** para aislamiento térmico de soldaduras.
* **Bridas y espiral organizadora:** para peinado y embridado de cables.

### 🧪 1.3 Instrumentación de medida y ajuste
* **Multímetro digital:** para comprobación de continuidad, tensión ($24\text{ V DC}$) y señal analógica ($0-10\text{ V}$).
* **Destornillador plano de ajuste:** mínimo, para potenciómetros de *Zero* y *Span* del transmisor.
* **Ordenador:** con TIA Portal V17/V18 (WinCC Basic) instalado.
* **Cable de red Ethernet RJ45:** categoría 5e/6 para programación por PROFINET.

---

## 🧱 2. Materiales y hardware del sistema

### 🤖 2.1 Control y automatización (PLC & HMI)
| Cantidad | Componente                       | Descripción / especificación                                                              |
------------------------------------------------------------------------------------------------------------------------------------------
| 1-2x     | **PLC Siemens S7-1200**          | CPU 1212C / 1214C DC/DC/DC con entradas analógicas $0-10\text{ V}$ e interfaces PROFINET. |
| 1x       | **Pantalla HMI SIMATIC**         | Siemens KTP400 / KTP700 Basic con puerto PROFINET.                                        |
| 1x       | **Fuente de alimentación**       | $24\text{ V DC} / 5\text{ A}$ montaje en carril DIN.                                      |
| 1x       | **Seta de parada de emergencia** | NC (Normalmente Cerrada) con enclavamiento para seguridad.                                |
| 1x       | **Botonera de control**          | Pulsadores de marcha/paro e indicadores luminosos de estado.                              |

### 🔬 2.2 Sensórica y acondicionamiento de señal
| Cantidad | Componente                         | Descripción / especificación                                                                   |
-------------------------------------------------------------------------------------------------------------------------------------------------
| 1x       | **Célula de carga de barra**       | Rango $20\text{ kg}$ o $50\text{ kg}$ (4 hilos: excitación y señal).                           |
| 1x       | **Transmisor analógico de célula** | Módulo DY220 (o equivalente) con alimentación $24\text{ V DC}$ y salida $0-10\text{ V}$.       |
| 2-3x     | **Sensores ópticos / inductivos**  | Detectores de presencia de pieza para cinta transportadora.                                    |

### ⚙️ 2.3 Mecánica y actuación
| Cantidad | Componente                                | Descripción / Especificación                                                     |
------------------------------------------------------------------------------------------------------------------------------------------
| 1x       | **Motor paso a paso NEMA 17**             | Motor de alto par para el eje de compresión vertical.                            |
| 1x       | **Driver de motor TB6600**                | Módulo de potencia ($9-42\text{ V DC}$) controlado por pulsos/dirección ($PTO$). |
| Varios   | **Perfiles de aluminio $2020$**           | Extruido V-Slot/T-Slot para el bastidor principal.                               |
| Varios   | **Escuadras y Tuercas T**                 | Uniones internas/externas y tornillería M4/M5 para perfilería.                   |
| 1x       | **Husillo $T8$ con Tuerca Latón**         | Paso de rosca para transmisión de avance vertical.                               |
| 2x       | **Varillas Lisas y Rodamientos**          | Varillas de acero $\varnothing 8\text{ mm}$ con rodamientos $LM8UU$ para guiado. |
| 1x       | **Acoplamiento Flexible $5-8\text{ mm}$** | Unión entre eje de motor NEMA 17 y husillo $T8$.                                 |
| 1x       | **Cinta Transportadora Didáctica**        | Línea de arrastre con motor y rodillos integrados.                               |
| 1x       | **Manipulador Pick & Place**              | Brazo o actuador para posicionamiento y evacuación de muestras.                  |
