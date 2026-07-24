<div align="center">
  <img src="enlace-a-tu-gif-animado.gif" width="800" alt="Vista previa del documento">
  <br><br>

  <h1>Análisis y Modelos Cuantitativos</h1>
  <p><i>Asignación Académica Desarrollada en LaTeX</i></p>
</div>

---

### Sobre el Documento

Este repositorio contiene el código fuente y la versión final de la investigación. El trabajo fue estructurado íntegramente en LaTeX para garantizar un rigor académico absoluto y una precisión visual impecable en la formulación matemática.

### Código Latex

\documentclass[12pt,a4paper]{report}

% --- PAQUETES BÁSICOS ---
\usepackage[utf8]{inputenc}
\usepackage[T1]{fontenc}
\usepackage[spanish,es-tabla]{babel}
\usepackage{mathptmx} % Fuente Times New Roman 12
\usepackage[margin=2.5cm]{geometry} % Márgenes de 2.5 cm
\usepackage{setspace}
\onehalfspacing % Interlineado 1.5

% --- PAQUETES DE MATEMÁTICAS Y GRÁFICOS ---
\usepackage{amsmath}
\usepackage{amssymb}
\usepackage{graphicx}
\usepackage{float}
\usepackage{caption}
\usepackage{multirow}

% --- PAQUETES PARA TABLAS ---
\usepackage{booktabs}
\usepackage{array}
\usepackage{longtable}
\usepackage{chngcntr} % Paquete para modificar contadores
\counterwithout{table}{chapter} % Numeración continua para tablas (1, 2, 3...)
\counterwithout{figure}{chapter} % Numeración continua para figuras (1, 2, 3...)

% --- NUEVO: CONFIGURACIÓN PARA QUE DIGA "Tabla X:" EN EL ÍNDICE ---
\usepackage{tocloft}
\renewcommand{\cfttabpresnum}{Tabla } % Añade la palabra "Tabla " antes del número
\renewcommand{\cfttabaftersnum}{:} % Añade los dos puntos ":" después del número
\addtolength{\cfttabnumwidth}{3.5em} % Amplía el espacio para que el texto nuevo no se superponga con el título
% -------------------------------------------------------------------

% --- PAQUETES DE BIBLIOGRAFÍA Y FORMATO ---
\usepackage{csquotes}
\usepackage{natbib}
\usepackage{hyperref}

\hypersetup{
    colorlinks=true,
    linkcolor=black,
    filecolor=black,      
    urlcolor=black,
    citecolor=black,
}

% --- CONFIGURACIÓN DE NIVELES DE TÍTULOS (APA 7 Y FORMATO SOLICITADO) ---
\usepackage{titlesec}

% Nivel 1 (Capítulos): Centrado, Negrita, Title Case. Capítulo X: Nombre en la misma línea.
\titleformat{\chapter}[block]
  {\centering\normalfont\LARGE\bfseries}
  {Capítulo \thechapter:}
  {0.5em}
  {}
\titlespacing*{\chapter}{0pt}{0pt}{20pt} 

% Nivel 2 (Subtítulos - \section): Alineado a la izquierda, Negrita, Title Case.
\titleformat{\section}[block]
  {\normalfont\Large\bfseries}
  {\thesection.}
  {0.5em}
  {}

% Nivel 3 (Subapartados - \subsection): Alineado a la izquierda, Negrita y Cursiva, Title Case.
\titleformat{\subsection}[block]
  {\normalfont\large\bfseries\itshape}
  {\thesubsection.}
  {0.5em}
  {}

% Nivel 4 (Sub-subapartados - \subsubsection): Alineado a la izquierda, Negrita, Title Case, con punto al final.
\titleformat{\subsubsection}[runin]
  {\normalfont\normalsize\bfseries}
  {\thesubsubsection.}
  {0.5em}
  {}[.]

% Nivel 5 (Párrafos - \paragraph): Alineado a la izquierda, Negrita y Cursiva, Title Case, con punto al final.
\titleformat{\paragraph}[runin]
  {\normalfont\normalsize\bfseries\itshape}
  {}
  {0em}
  {}[.]


\begin{document}

% ==============================================================================
% ==============================================================================
% ==============================================================================
% PORTADA ACTUALIZADA (Integrantes ordenados alfabéticamente por apellido)
% ==============================================================================
\begin{titlepage}
    \centering
    \vspace*{1cm}
    
    {\Large \textbf{Universidad Nacional Santiago Antúnez de Mayolo}}\\[0.3cm]
    {\large \textbf{Facultad de Administración}}\\[0.8cm]
    
    % Logo institucional (Requiere el archivo unasam.jpg en el proyecto de Overleaf)
    \includegraphics[width=3.5cm]{unasam.jpg}\\[1cm]
    
    {\Large \textbf{Simulación de Eventos Discretos y Método de Monte Carlo: Fundamentos, Aplicación y Análisis para la Toma de Decisiones Empresariales}}\\[1cm]
    
    {\large \textbf{Curso:}}\\[0.3cm]
    {\large Análisis Cuantitativo para la Toma de Decisiones II}\\[0.8cm]
    
    {\large \textbf{Docente:}}\\[0.3cm]
    {\large Dextre Martínez William Rene}\\[0.8cm]
    
    {\large \textbf{Integrantes:}}\\[0.3cm]
    {\large
    Cruz Anampi, Fatima Fiorella\\
    Gargate Tarazona, Edward Lucio\\
    Gomero Tito, Jorge Jesus\\
    Iparraguirre Marino, Nilcod Miriem\\
    Moreno Robles, Rubi Ximena\\
    Támara Ramírez, Anghelo Jhuliano
    }\\[1.5cm]
    
    \vfill
    {\large Huaraz, Perú}\\[0.3cm]
    {\large \the\year}
\end{titlepage}

% ==============================================================================
% ÍNDICES
% ==============================================================================
\pagenumbering{roman}

\tableofcontents
\newpage

\listoftables
\newpage



% ==============================================================================
% CUERPO DEL DOCUMENTO
% ==============================================================================
\pagenumbering{arabic}

% ------------------------------------------------------------------------------
% INICIO DE LA INTRODUCCIÓN
% ------------------------------------------------------------------------------
\chapter*{Introducción}
\addcontentsline{toc}{chapter}{Introducción}

El entorno empresarial contemporáneo se desenvuelve en escenarios caracterizados por una alta complejidad operativa y una exposición constante a la variabilidad, fundamentar las decisiones estratégicas exclusivamente en la intuición, en datos históricos estáticos o en promedios aritméticos resulta insuficiente para mitigar el riesgo. Alterar directamente un sistema real para evaluar nuevas políticas corporativas, modificar líneas de producción o rediseñar la cadena de suministro suele ser prohibitivo debido a los altos costos involucrados, la interrupción de las operaciones y la posibilidad de fracaso comercial. La simulación computacional se posiciona como un laboratorio empírico que permite formular, experimentar y analizar alternativas operativas y financieras.

La simulación de eventos discretos y el método de Monte Carlo son dos de las herramientas metodológicas más rigurosas dentro de la simulación de eventos discretos se especializa en modelar el comportamiento dinámico de los sistemas a lo largo del tiempo, esta técnica sirve para identificar cuellos de botella, medir la longitud y el tiempo de espera en las colas, evaluar la capacidad instalada y optimizar los flujos de trabajo en operaciones donde los cambios de estado ocurren en momentos cronológicos específicos.

El método de Monte Carlo aborda la incertidumbre inherente a las variables de negocio a través de la teoría de la probabilidad. En lugar de depender de estimaciones puntuales para factores críticos como la demanda del mercado, las fluctuaciones de costos o los tiempos de entrega logísticos, este método emplea distribuciones estadísticas para generar miles de escenarios aleatorios. Las iteraciones computacionales revelan resultados posibles, cuantificando la probabilidad de ocurrencia de escenarios extremos y facilitando un análisis profundo de sensibilidad y exposición al riesgo en la dirección de proyectos e inversiones. Los eventos discretos estructuran la lógica operativa del modelo, la incorporación de variables estocásticas de Monte Carlo que permite evaluar cómo la volatilidad del entorno impacta en el rendimiento global de esta forma los datos aislados en modelos predictivos, así reduciendo la asimetría de información y fundamentando la toma de decisiones sobre bases estadísticas verificables. En la administración, el dominio y la interpretación de estas técnicas trascienden la mera competencia informática; constituyen una habilidad gerencial indispensable para diseñar organizaciones ágiles, eficientes y financieramente resilientes.

El objetivo de este trabajo de investigación es analizar los fundamentos teóricos, la estructura metodológica y la aplicación práctica de la simulación de eventos discretos y el método de Monte Carlo, demostrando su utilidad analítica conjunta como soporte para la toma de decisiones empresariales bajo condiciones de riesgo e incertidumbre, así que el trabajo se organiza en siete capítulos. El Capítulo I establece las bases conceptuales, los elementos de la simulación, el Capítulo II profundiza en la mecánica interna, los componentes y los indicadores de desempeño propios de los sistemas de eventos discretos, el Capítulo III trata de los fundamentos probabilísticos del método de Monte Carlo orientados a la evaluación de escenarios, el Capítulo IV explica la complementariedad técnica y analítica, el Capítulo V detalla las fases metodológicas estandarizadas para la construcción de modelos y contrasta las herramientas computacionales, el Capítulo VI se desarrolla un caso práctico, ilustrando el proceso completo desde la identificación de variables hasta la selección de una alternativa óptima, el Capítulo VII expone las aplicaciones organizacionales de estas técnicas en áreas funcionales clave.

% ------------------------------------------------------------------------------
% CAPÍTULO 1
% ------------------------------------------------------------------------------
\setcounter{chapter}{0}
\chapter{Fundamentos de la Simulación}

\section{Concepto e Importancia de la Simulación}
La simulación constituye una técnica analítica orientada a imitar el funcionamiento de un sistema real o propuesto a lo largo del tiempo. La construcción de un modelo lógico-matemático que captura las interacciones históricas y predecibles de las entidades organizacionales, permitiendo realizar experimentos sobre dicho modelo en lugar de intervenir directamente en el sistema físico (Greasley, 2003). Resulta indispensable cuando los problemas empresariales son demasiado complejos para ser evaluados mediante ecuaciones analíticas exactas o teoría de colas básica.

El concepto de simulación trasciende la mera programación informática; se posiciona como un laboratorio organizacional. La simulación faculta a los tomadores de decisiones para formular interrogantes del tipo «¿qué pasaría si...?» bajo condiciones estrictamente controladas en lugar de implementar una nueva política de inventarios, rediseñar la distribución física de un almacén o alterar la dotación de personal asumiendo riesgos financieros y operativos reales.

Las empresas operan en entornos estocásticos donde la demanda fluctúa, las maquinarias sufren averías y los tiempos de suministro logístico varían. Los enfoques de planificación determinísticos, basados exclusivamente en promedios aritméticos, suelen fallar al intentar capturar esta variabilidad, la simulación integra estas fluctuaciones estadísticas naturales, revelando no solo el desempeño esperado del sistema, sino también la probabilidad de ocurrencia de escenarios críticos, sobrecostos (Robinson, 2012).

La Tabla 1 detalla las principales dimensiones que justifican LA estratégica frente a los métodos de análisis tradicionales.

\begin{table}[H]
\centering
\caption{Dimensiones de la estratégica en el marco empresarial}
\begin{tabular}{p{5cm} p{10cm}}
\toprule
\textbf{Dimensión} & \textbf{Impacto en la Toma de Decisiones} \\
\midrule
Reducción de riesgos operacionales & Evalúa el impacto de decisiones financieras sin interrumpir las operaciones en curso. \\
Compresión del tiempo analítico & Facilita la observación de dinámicas organizacionales a largo plazo \\
Gestión de variabilidad e incertidumbre & Reemplaza el análisis de variables estáticas por distribuciones de probabilidad \\
Visibilidad de interdependencias & Evidencia cuellos de botella que surgen de la interacción simultánea entre distintos departamentos. \\
\bottomrule
\end{tabular}
\begin{flushleft}
\footnotesize
\textit{Nota.} Elaboración propia
\end{flushleft}
\end{table}

La simulación exige un análisis crítico riguroso y de los resultados obtenidos es proporcional a la exactitud de los datos de entrada y a la validez lógica del modelo construido. Un modelo deficientemente puede generar una falsa sensación de seguridad, es por ello preciso mencionar que la simulación no sustituye el juicio del que va tomar decisiones lo que hace es actuar como un complemento técnico que proporciona evidencia estadística que justifica la elección de la alternativa.

\section{Modelos y Elementos de Simulación}
Un sistema se concibe como una agrupación de elementos ya sean personas, maquinarias, capital o flujos de información, y estos interactúan de manera interdependiente para cumplir un propósito organizacional (Law, 2015). La mayoría de los entornos empresariales presentan una dificultad que imposibilita su resolución mediante métodos matemáticos exactos, es así que el analista debe recurrir a la construcción de un modelo.

La implementación de software es una abstracción lógico matemática que captura exclusivamente aquellas características del sistema real que son pertinentes para el problema de negocio que se pretende resolver. El modelamiento no es un ejercicio de réplica exhaustiva, sino de simplificación estratégica. Desde la perspectiva de la administración, un modelo excesivamente detallado incrementa los costos de programación, el tiempo de desarrollo y la demanda computacional sin aportar necesariamente mayor precisión a la toma de decisiones. Por el contrario, un modelo demasiado simplificado corre el riesgo de perder validez predictiva y credibilidad gerencial (Robinson, 2014).

La rigurosidad de estos elementos determina la fidelidad con la que el entorno virtual imita la realidad operativa (Banks et al. 2014). A continuación, se detallan los elementos cardinales que constituyen la base del modelamiento:

\begin{itemize}
    \item \textbf{Entidades:} Representan los objetos dinámicos que fluyen, demandan servicios y transitan a través del sistema. 
    \item \textbf{Atributos:} Constituyen las características particulares asociadas individualmente a cada entidad, permitiendo al sistema lógico diferenciar su tratamiento.
    \item \textbf{Recursos:} Son los agentes, equipos o espacios físicos que proporcionan un servicio a las entidades. 
    \item \textbf{Variables de estado:} Comprenden el conjunto mínimo de variables necesarias para describir la situación exacta del sistema en un instante de tiempo cronológico determinado. 
    \item \textbf{Eventos:} Se definen como ocurrencias instantáneas que alteran el valor de al menos una variable de estado del sistema.
\end{itemize}

Estos elementos con una manipulación controlada de los mismos aumenta la capacidad de los recursos, modificar la regla de prioridad de los atributos o alterar la tasa de llegada de los eventos mediante el cual se logra evaluar y optimizar distintas alternativas estratégicas.

\section{Tipos de Simulación}
Comprender la clasificación de estos modelos es el primer paso crítico en el diseño de cualquier experimento virtual.

En la literatura de la investigación de operaciones, los modelos de simulación se clasifican tradicionalmente a través de tres dimensiones analíticas fundamentales, las cuales determinan la arquitectura del modelo y el tipo de respuestas que este puede proporcionar a la gerencia (Law, 2015). Estas dimensiones evalúan la dependencia del tiempo, el tratamiento de la incertidumbre y la naturaleza del cambio en las variables de estado.

La primera dimensión, que representa la división más básica en la estructuración de un modelo, clasifica a las simulaciones en estáticas o dinámicas:

\begin{itemize}
    \item \textbf{Modelos de simulación estática:} Son aquellos que representan un sistema en un punto específico en el tiempo, o bien, donde el avance cronológico no juega un papel relevante en el análisis. En el ámbito corporativo, el cálculo del Valor Actual Neto (VAN) de un proyecto de inversión bajo riesgo o la estimación de la rentabilidad de un portafolio de acciones son ejemplos clásicos. En estos casos, el administrador no está interesado en el minuto a minuto del flujo de caja, sino en el resultado acumulado o final bajo condiciones de incertidumbre. El método de Monte Carlo es el máximo exponente de esta categoría (Banks et al. 2014).
    \item \textbf{Modelos de simulación dinámica:} En contraste, estos modelos representan sistemas que evolucionan de manera continua o discreta a lo largo del tiempo. Aquí, la variable temporal (reloj de simulación) es el eje central del modelo. Son indispensables cuando la gerencia necesita observar cómo fluctúa la longitud de una fila de espera en un banco durante la jornada laboral, o cómo se acumula el inventario en tránsito a lo largo de las semanas en una cadena de suministro.
\end{itemize}

Para ofrecer una visión integral de la taxonomía, la Tabla 2 sintetiza las tres dimensiones principales. Es pertinente señalar que un modelo computacional robusto es siempre el resultado de la combinación de estas tres dimensiones.

\begin{table}[H]
\centering
\caption{Dimensiones fundamentales para la clasificación de modelos de simulación}
\begin{tabular}{p{4.5cm} p{5cm} p{5.5cm}}
\toprule
\textbf{Dimensión} & \textbf{Clasificación} & \textbf{Aplicación Administrativa Típica} \\
\midrule
\multirow{2}{=}{Evolución temporal} & Estática (Independiente del tiempo) & Evaluación de riesgo financiero, auditoría estocástica (Monte Carlo). \\
 & Dinámica (Dependiente del tiempo) & Gestión de colas, planificación de la producción, logística. \\
\midrule
\multirow{2}{=}{Tratamiento de la variabilidad} & Determinística (Ausencia de azar) & Programación lineal exacta, presupuestos fijos. \\
 & Estocástica (Presencia de azar) & Pronóstico de demanda, tiempos de falla de maquinaria. \\
\midrule
\multirow{2}{=}{Cambio de estado} & Discreta  & Manufactura \\
 & Continua & Procesamiento de petróleo. \\
\bottomrule
\end{tabular}
\begin{flushleft}
\footnotesize
\textit{Nota.} Elaboración propia
\end{flushleft}
\end{table}

\section{Simulación Determinística y Estocástica}
La clasificación de los modelos analíticos radica en el tratamiento de la incertidumbre y la naturaleza de sus variables de entrada. Dependiendo de si el sistema excluye o incorpora la aleatoriedad, la simulación se clasifica como determinística o estocástica, esto determina el nivel de confianza y la validez estadística de las decisiones gerenciales que se fundamenten en el modelo (Law, 2015).

Un conjunto específico de datos de entrada producirá invariablemente el mismo resultado de salida, sin importar cuántas veces se ejecute el experimento (Banks et al. 2014). Es así que resulta útil para estructurar procesos rígidamente controlados donde las desviaciones son nulas o irrelevantes. Ejemplos clásicos incluyen la formulación de un cuadro de amortización de deuda corporativa con tasas de interés fijas o la programación matemática lineal para asignar recursos bajo restricciones exactas.

La capacidad predictiva se ve severamente mermada al enfrentar la complejidad del mundo empresarial real, donde la variabilidad es inherente a casi todos los procesos, es así que una práctica común es que consiste en sustituir variables inciertas por sus promedios aritméticos histórico, esto podría incurrir en un sesgo analítico. Diseñar la capacidad instalada de una planta de producción asumiendo que los proveedores entregarán la materia prima exactamente en tres días, ignorando las fluctuaciones reales de la cadena de suministro, hace que las estimaciones de desempeño sean imperceptibles al riesgo de desabastecimiento, es así que si ignoramos la variabilidad del entorno conduce a subestimar el riesgo estratégico y compromete la viabilidad de los proyectos.

Un modelo estocástico se define como aquel que incorpora una o más variables aleatorias en sus parámetros de entrada. En lugar de utilizar valores fijos, el analista emplea distribuciones de probabilidad como la normal, exponencial o triangular, que capturan matemáticamente la variable (Law, 2015). Por eso factores como la demanda diaria de un producto, el tiempo de reparación de un servidor informático o la volatilidad de los precios de los insumos exigen un tratamiento estocástico.

La inclusión de la aleatoriedad transforma radicalmente la interpretación de la salida del sistema. Dado que los inputs (Entradas) cambian según probabilidades definidas, los outputs (Salidas) de la simulación estocástica son estimaciones estadísticas. Podemos decir que la ejecución de una única simulación carece de representatividad entonces es necesario para tomar decisiones, se debe diseñar experimentos que involucren múltiples iteraciones independientes del modelo. Dicho eso el enfoque iterativo, central tanto en los eventos discretos como en el método de Monte Carlo, genera intervalos de confianza y perfiles de riesgo que enriquecen el juicio directivo. A través de las simulaciones, las proyecciones adoptan un análisis de escenarios basado en la probabilidad de ocurrencia, mejorando la resiliencia de la planificación.

\section{Simulación Continua y Discreta}
Para clasificar un modelo analítico se refiere a la naturaleza de la evolución de sus componentes de estado a lo largo del tiempo. Esta característica define si el es de simulación continua o discreta, determinando el tipo de software requerido para su ejecución (Law, 2015).

En la simulación continua, el sistema cambia de manera ininterrumpida respecto al tiempo. Este comportamiento se modela típicamente mediante ecuaciones diferenciales que calculan tasas de cambio fluidas, es indispensable para analizar procesos físicos indivisibles, como el flujo de petróleo en una refinería, las reacciones químicas o las variaciones térmicas en un sistema de refrigeración. 

La simulación discreta (o de eventos discretos) modela en los que las variables de estado cambian instantáneamente en puntos separados en el tiempo. Entre un evento y el que le sigue, este permanecerá sin alteraciones, independientemente del tiempo transcurrido, es así que estos puntos de cambio se denominan eventos, la inmensa mayoría de los procesos muestran este comportamiento: el inventario disminuye de un día para otro cuando se despacha una orden, una máquina cambia de estado de activo a inoperativo en el instante en que inicia el procesamiento de una pieza, y la longitud de una cola aumenta en el momento exacto en que llega un nuevo cliente.

La elección entre continuo y uno discreto no depende estrictamente de la naturaleza física del sistema, sino del objetivo del estudio. Por ejemplo, el flujo de vehículos en una autopista puede modelarse de forma continua para analizar la densidad del tráfico o de forma discreta modelando cada vehículo individual para evaluar tiempos exactos de espera en un peaje, entonces para la toma de decisiones, la simulación de eventos discretos predomina, dado que permite rastrear individualmente entidades, recursos y cuellos de botella operativos con alta granularidad (Pidd, 2004).

\sectionsection{Ventajas y Limitaciones de la Simulación}
La toma de decisiones no es segura ni única, como cualquier herramienta cuantitativa, presenta fortalezas que justifican su uso, pero también limitaciones que se debe considerar para evitar interpretaciones erróneas (Robinson, 2014).

Las ventajas que puede suscitar, es la capacidad de realizar un análisis de interdependencias. Mientras que trabajos en hojas de cálculo como en el excel que evalúan variables de forma lineal y aislada, la simulación logra capturar los efectos en cascada que una decisión genera sobre el resto, eso quiere decir que permite la compresión o expansión del tiempo; así que se puede simular cinco años de operaciones de un nuevo centro de distribución en escasos minutos de procesamiento con un software (Banks et al. 2014). Dicho esto podemos mencionar que modelos de simulación modernos actúan como potentes herramientas de comunicación: las animaciones visuales (en 2D o 3D) facilitan que los stakeholders sin formación matemática comprendan la dinámica de los cuellos de botella operativos y apoyen financieramente las propuestas de mejora (Jahangirian et al. 2010).

La simulación presenta limitaciones técnicas y económicas considerables, como, la construcción de un modelo aleatorio riguroso exige una inversión sustancial de tiempo, como la de capital humano especializado y recursos informáticos, eso puede afectar que en ocasiones, para problemas analíticos simples, el costo de desarrollar el modelo puede superar el beneficio de la decisión a tomar,además de ello existe el riesgo de la "falsa precisión". Un modelo desarrollado con software siempre arrojará un resultado numérico, incluso si los datos de entrada son deficientes o la lógica es incorrecta, entonces esta situación conocido en informática como GIGO (Garbage In, Garbage Out), exige que se valide rigurosamente la procedencia de la información histórica (Law, 2015).

La Tabla 3 sistematiza estos factores, proporcionando un marco de referencia para evaluar la pertinencia de utilizar la simulación frente a otros métodos de análisis.

\begin{table}[H]
\centering
\caption{Análisis de las ventajas y limitaciones de la simulación}
\begin{tabular}{p{7.5cm} p{7.5cm}}
\toprule
\textbf{Ventajas Estratégicas} & \textbf{Limitaciones y Riesgos} \\
\midrule
Capacidad para evaluar situaciones complejas donde las soluciones usando análisis son imposibles. & Altos costos de desarrollo y requerimiento de personal especializado en investigación de operaciones. \\
Integración del riesgo mediante variables aleatorias, siendo más de las estimaciones basadas en promedios. & Los resultados son estimaciones estadísticas (intervalos), no respuestas exactas u óptimas garantizadas. \\
Experimentación sin interrupción, protegiendo el manejo continuo del capital y el nivel de servicio. & Dependencia crítica de la calidad de los datos históricos de entrada (riesgo de sesgo de validación). \\
\bottomrule
\end{tabular}
\begin{flushleft}
\footnotesize
\textit{Nota.} Elaboración propia a partir de los estudios de Banks et al. (2014) y Robinson (2014).
\end{flushleft}
\end{table}

\section{Proceso General de Desarrollo de una Simulación}
El desarrollo de un modelo de simulación en el ámbito corporativo no es un ejercicio exclusivamente de programación, sino un proyecto de investigación aplicada. El éxito de este proyecto depende de la rigurosidad con la que se ejecute una metodología estructurada por fases. Si un analista se apresura a escribir código sin haber definido claramente el alcance del problema junto con la gerencia, el modelo resultante, aunque matemáticamente perfecto, no resolverá el dilema de negocio (Sargent 2013).

Diversas propuestas dentro de la literatura académica consensúan un ciclo de vida estándar compuesto por fases iterativas (Law, 2015). El proceso general abarca los siguientes grandes hitos:

\begin{enumerate}
    \item \textbf{Formulación del problema y planificación:} Es la parte más importante. Los que se encargan de realizar o tomar decisiones deben definir conjuntamente los objetivos del estudio, los indicadores clave de desempeño (KPIs) a evaluar y el nivel de detalle que se necesita.
    \item \textbf{Recolección de datos y definición del modelo conceptual:} Es el paso donde se hace el levantamiento de información, por ejemplo si estamos hablando en una empresa de servicios, tenemos que recolectar datos de los tiempos de servicio, tasas de llegada, etc.) y como este sigue la secuencia que se puede representar a través de diagramas de flujo. En esta etapa se decide qué variables serán estocásticas y a qué distribuciones de probabilidad se ajustarán.
    \item \textbf{Construcción del modelo:} Consiste en traducir el modelo lógico a un lenguaje de programación que actualmente puede ser Python/SimPy o a un software de propósito específico como Arena, FlexSim o herramientas como Crystal Ball para Monte Carlo.
    \item \textbf{Verificación y validación:} La verificación puede lograr asegurar que el código que usemos funcione correctamente (sin errores de sintaxis o lógica). La validación, comprueba estadística y que el modelo representa con precisión al sistema real, garantizando que sus predicciones sean confiables.
    \item \textbf{Diseño de experimentos y ejecución:} Una vez validado, el modelo se utiliza para simular las diferentes alternativas (escenarios). Dado su carácter estocástico o aleatorio, se debe determinar el número adecuado de iteraciones para que los resultados resulten con una significancia estadística.
    \item \textbf{Análisis de resultados e implementación:} Los datos de salida se someten a análisis de carácter inferencial para comparar el desempeño de los escenarios, porque no solo es desarrollar números sin significado es por ello necesario darle una interpretación que ayude a que la toma de decisión sea más sencilla, posterior a eso se elabora un informe ejecutivo que fundamenta la recomendación facilitando su implementación.
\end{enumerate}

Hay que destacar que este proceso no se da de forma lineal o en eventos continuos es habitual y no hay problema si se retorna a etapas previas si durante la validación se detectan inconsistencias en los datos o si se solicita evaluar un nuevo escenario. El dominio de esto garantiza que la simulación trascienda y se consolide como un activo analítico para la toma de decisiones.

% ------------------------------------------------------------------------------
% CAPÍTULO 2
% ------------------------------------------------------------------------------
\chapter{Simulación de Eventos Discretos}

\section{Concepto y Características de los Eventos Discretos}
Simulación de eventos discretos (SED) trata de como un sistema a lo largo del tiempo, en el cual las variables de estado cambian de manera instantánea y exclusiva en puntos cronológicos separados (Law, 2015). A diferencia de los eventos continuos, donde la evolución es fluida e ininterrumpida, en un modelo discreto el permanece estrictamente inalterado durante el intervalo de tiempo que transcurre de un evento y el siguiente. Un evento, se puede decir que es una ocurrencia instantánea que altera la situación operativa de la organización; ejemplos que podemos decir en el mundo real se podría considerar como la llegada de un cliente a una sucursal bancaria, la avería de una máquina empaquetadora o la recepción de un lote de mercancia en el almacén.

Una de las características que distingue a esta metodo es su mecanismo de de lapso temporal, conocido como el avance del tiempo hasta el próximo evento (next-event time advance). Es preciso entonces mencionar que este hecho, el reloj de la simulación no avanza en intervalos regulares, sino que el algoritmo identifica el próximo evento programado en la lista de sucesos y hace que el reloj salte directamente hacia ese instante (Pidd, 2004). Esta hecho particular otorga a la técnica una altísima eficiencia de procesamiento en análisis de datos, ya que permite omitir los periodos de inactividad o los tiempos muertos, logrando así simular meses o incluso años de operación corporativa en escasos segundos.

Las características intrínsecas de los eventos discretos resultan idóneas para representar redes de procesos donde múltiples entidades compiten simultáneamente por el acceso a recursos finitos, a diferencia de las ecuaciones estáticas, la que distingue al evento discreto, es que permite al analista rastrear con extremo detalle el ciclo de vida de cada entidad individual dentro de la empresa (Greasley, 2003). De este modo, es posible cuantificar con rigor si se desea tomar decisiones por ejemplo en el ambito de las empresas, algunas de ellas son el tiempo total de permanencia, la longitud máxima de una fila de espera o los porcentajes de ociosidad del personal.

Cuando se usa esta técnica supera las limitaciones inherentes a la teoría de colas, ya que las fórmulas analíticas clásicas exigen supuestos matemáticos rígidos como llegadas estrictamente exponenciales o un estado estacionario perpetuo, la simulación de eventos discretos posee la flexibilidad necesaria para incorporar horarios de trabajo, pausas de mantenimiento, prioridades de atención y variaciones estacionales en la demanda (Robinson, 2012). La base cuantitativa es indispensable para justificar decisiones estratégicas de alta inversión, como la expansión de la capacidad instalada o el rediseño físico de la cadena de suministro, antes de intervenir sobre la realidad que pueda existir dentro de una empresa.

\section{Elementos de un Modelo de Eventos Discretos}
Si bien en el capítulo anterior se abordaron los componentes generales de la simulación, la arquitectura específica de los eventos discretos requiere una infraestructura computacional particular para gestionar el tiempo y la incertidumbre. Para que un modelo discreto funcione como un laboratorio empresarial fiable, debe integrar elementos lógicos y estadísticos que interactúen dinámicamente. Según Law (2015) y Banks et al. (2014), los componentes exclusivos de un modelo de eventos discretos son los siguientes:

\begin{itemize}
    \item \textbf{Reloj de simulación (Simulation Clock):} Es la variable que mantiene el registro del valor actual del tiempo simulado. En la administración de operaciones, este reloj no está vinculado al tiempo físico del procesador, sino a la unidad de medida del negocio (segundos, horas, días).
    \item \textbf{Lista de eventos futuros (LEF):} Constituye el "cerebro" del modelo. Es una estructura de datos dinámica que almacena y ordena cronológicamente todos los eventos que están programados para ocurrir en el futuro. A medida que el sistema opera, la LEF se actualiza constantemente: elimina los eventos que ya ocurrieron y programa nuevos sucesos (por ejemplo, cuando una máquina inicia el procesamiento de una pieza, la LEF programa inmediatamente el evento de "finalización" sumando el tiempo de procesamiento al reloj de simulación actual).
    \item \textbf{Colas (Queues):} En sistemas discretos, las colas son espacios de almacenamiento lógico donde las entidades esperan cuando los recursos que requieren no están disponibles. Su gestión incluye una disciplina de atención, siendo la más común en negocios la política FIFO (First In, First Out), aunque en escenarios como la atención de urgencias médicas o manufactura de alta prioridad se aplican disciplinas basadas en atributos específicos de la entidad.
    \item \textbf{Acumuladores estadísticos:} Son variables invisibles para la lógica del sistema, pero vitales para la toma de decisiones. Su función es registrar continuamente los datos del desempeño operativo durante la ejecución. Almacenan información como la sumatoria de los tiempos de espera, la cantidad total de entidades procesadas o el tiempo acumulado que un recurso estuvo ocupado, y podemos decir que la simulación son responsables de generar los indicadores(KPIs).
\end{itemize}

Estos elementos garantiza que al momento de someter a un análisis matemática no pierda su vínculo con la realidad. Un error común en la planificación de proyectos es omitir la capacidad finita de las colas físicas o ignorar las políticas de priorización, lo que invariablemente distorsiona los resultados estadísticos arrojados por el modelo (Pidd, 2004).

\section{Funcionamiento y Dinámica de un Sistema de Eventos Discretos}
La dinámica interna de un sistema de eventos discretos podemos decir que sirve de mucha ayuda si lo queremos hacer uso en la parte administrativa ya que le permite interpretar cómo el software transforma datos de entrada (aleatorios) en predicciones de desempeño empresarial. La ejecución de un modelo discreto no es un proceso continuo, sino un bucle algorítmico cíclico guiado estrictamente por la ocurrencia de eventos.

La simulación opera mediante una lógica de avance secuencial que puede explciarse en un ciclo de cinco pasos, iterado repetidamente hasta alcanzar la condición de parada del modelo y si lo ponemos esto en un entorno organizacional podemos tomar ejemplos como el fin de la jornada laboral o la finalización de un periodo de producción anual.

\begin{enumerate}
    \item \textbf{Inicialización:} Define el estado inicial, así que se establece el reloj de simulación en cero, aquí como ejemplo podemos mencionar los recursos ociosos, colas vacías, etc. y se programa los primeros eventos en la Lista de Eventos Futuros (LEF), como la llegada de la primera entidad.
    \item \textbf{Avance del tiempo:} El algoritmo consulta la LEF, identifica cuál es el evento l que tiene el menor tiempo programado y hace que el reloj de simulación salte exactamente a ese instante. Los intervalos de tiempo donde no ocurre nada son simplemente ignorados, lo que optimiza drásticamente cuando lo desarrollamos con un software.
    \item \textbf{Actualización del estado:} Al procesar el evento, el software modifica las variables de estado correspondientes. Si el evento es una "llegada", la entidad se asigna a un recurso (cambiando su estado a ocupado) o se envía a una cola. Si el evento es una salida, el recurso se libera y queda disponible para atender a la siguiente entidad en la fila.
    \item \textbf{Actualización estadística:} Luego de los 3 primeros pasos, los acumuladores estadísticos registran el tiempo de espera, el nivel de inventario o la utilización del recurso en ese instante preciso, almacenando la evidencia matemática para el análisis.
    \item \textbf{Generación de nuevos eventos:} La ejecución del evento actual suele ocacionar eventos futuros, como, la llegada de un cliente provoca automáticamente la generación aleatoria del tiempo de llegada del siguiente cliente, insertando este nuevo suceso en la lista de eventos futuros. Una vez finalizamos este paso, el ciclo retorna a la fase de avance del tiempo.
\end{enumerate}

Podemos decir que la simulación de eventos discretos es la herramienta que gestiona de manera eficiente que permite capturar la variabilidad de procesos complejos, donde tenemos la saturación escalonada de los servidores, el efecto látigo en la cadena de suministros, los bloqueos en líneas de ensamblaje, etc. que son matemáticamente imposibles de evaluar mediante el uso de promedios simples u hojas de cálculo estáticas (Jahangirian et al. 2010). 

\section{Variables de Entrada y Distribuciones de Probabilidad}
La veracidad o aceptabilidad predictiva de un modelo de simulación de eventos discretos depende directamente de la calidad de los datos que lo alimentan, los procesos rara vez son determinísticos y si lo ponemos en entornos de las empresas podemos encontrar ejemplos como; el tiempo que tarda un cajero en atender a un cliente o el intervalo de llegada entre pedidos fluctúan continuamente. Para modelar esta realidad, el analista debe sustituir las estimaciones estáticas por variables estocásticas, modeladas a través de distribuciones de probabilidad teóricas o empíricas (Kelton et al., 2015).

El proceso de caracterización de las variables de entrada (input modeling) consta de tres fases: la recolección de datos históricos, la selección de una familia de distribuciones y la prueba de bondad de ajuste. En la administración de operaciones, las distribuciones más utilizadas tienen aplicaciones específicas según la naturaleza del evento:

\begin{itemize}
    \item \textbf{Distribución Exponencial:} Empleada casi universalmente para modelar el tiempo entre llegadas de entidades al sistema (por ejemplo, clientes ingresando a una sucursal o llamadas entrantes a un call center), asumiendo que los eventos ocurren de manera independiente.
    \item \textbf{Distribuciones Normal, Triangular y PERT:} Utilizadas frecuentemente para modelar tiempos de servicio o de procesamiento cuando existen estimaciones claras de un tiempo mínimo, máximo y más probable, especialmente útiles cuando se carece de un volumen robusto de datos históricos.
    \item \textbf{Distribuciones Discretas (Poisson o Binomial):} Aplicadas cuando la variable de interés asume valores enteros, como el número de artículos defectuosos en un lote o la cantidad de clientes que llegan en un grupo.
\end{itemize}

Asignar al azar una distribución invalida completamente el modelo, es aquí donde enfatiza la necesidad de someter los datos históricos a pruebas de ajuste, como Kolmogorov-Smirnov o Chi-cuadrado, para demostrar estadísticamente que la distribución seleccionada representa con precisión el comportamiento. Si se fundamenta una decisión de inversión en un modelo cuyas variables de entrada no han sido validadas, el riesgo de fracaso es muy alto.

\section{Indicadores de Desempeño del Sistema}
Mientras que las variables de entrada y la lógica del modelo constituyen la arquitectura del sistema, los indicadores de desempeño (KPIs) representan las respuestas del laboratorio virtual a las interrogantes gerenciales. Durante la ejecución de un modelo discreto, los acumuladores estadísticos registran el comportamiento de las entidades y recursos, traduciendo la dinámica computacional en métricas administrativas comprensibles y accionables (Banks et al. 2014).

A diferencia de un balance financiero que muestra el resultado al final del periodo, la simulación de eventos discretos arroja indicadores operativos dinámicos. La Tabla 4 presenta la equivalencia entre las variables de salida clásicas del modelo computacional y los KPIs críticos para la toma de decisiones empresariales.

\begin{table}[H]
\centering
\caption{Relación entre variables de salida de simulación y decisiones administrativas}
\begin{tabular}{p{4.5cm} p{5.5cm} p{5.5cm}}
\toprule
\textbf{Salida del Modelo} & \textbf{KPI Administrativo} & \textbf{Aplicación en Toma de Decisiones} \\
\midrule
Tiempo en cola (Wait Time) & Nivel de servicio al cliente. & Justificar la contratación de personal adicional en horas pico. \\
Longitud de la cola (Queue Length) & Capacidad de la sala de espera / saturación del sistema. & Rediseño del layout físico o ampliación de instalaciones. \\
Utilización de recursos (Utilization) & Porcentaje de tiempo productivo vs. ocioso. & Equilibrar cargas de trabajo o eliminar turnos innecesarios. \\
Tiempo en el sistema (Cycle Time) & Lead time o tiempo total de respuesta. & Mejorar la entrega comercial a los clientes. \\
Throughput & Unidades producidas o clientes atendidos por turno. & Evaluar si se aceptan nuevos contratos de gran volumen. \\
\bottomrule
\end{tabular}
\begin{flushleft}
\footnotesize
\textit{Nota.} Adaptado los conceptos de medición de desempeño de Greasley (2003) y Kelton et al. (2015).
\end{flushleft}
\end{table}

El valor diferencial de estos indicadores son aleatorias, es así que el modelo no entrega un número exacto, sino un intervalo de confianza y valores máximos/mínimos, lo que permite evaluar escenarios extremos (el "peor de los casos") y diseñar planes de contingencia para poder mitigar lo errores que se puedan generar.

\section{Construcción, Verificación y Validación de Modelos}
La transformación de un flujo corporativo en la utilización de software exige un rigor metodológico estricto para evitar conclusiones sesgadas. En la simulación de eventos discretos, este se evidencia en los procesos paralelos de construcción, verificación y validación, los cuales garantizan que el modelo sea técnica y conceptualmente correcto (Sargent, 2013).

La construcción inicia con un modelo conceptual (generalmente mediante flujogramas matriciales), identificando entidades, rutas y restricciones. Enseguida, este concepto se codifica utilizando lenguajes de programación o software especializado.

La verificación es un proceso informático y matemático. Consiste en asegurar que el modelo realizado haya sido programado correctamente y no contenga errores lógicos. Un modelo verificado es aquel que ejecuta fielmente la lógica diseñada por el analista: las entidades no desaparecen sin justificación, las capacidades de los recursos no se excedan y el reloj avanza sin pausas cíclicos (Law, 2015). En síntesis, responde a la pregunta: «¿Se construyó el modelo correctamente?».

La validación, por otro lado, es un proceso empírico y gerencial. Su propósito es demostrar que el comportamiento del modelo es una representación precisa y creíble del sistema real que pretende imitar (Sargent 2013). Responde a la pregunta: «¿Se construyó el modelo correcto?». Para lograr esto, el administrador debe comparar las salidas del modelo bajo condiciones actuales con los datos históricos reales de la empresa (Prueba de Turing). Si la simulación predice que una fábrica producirá 500 unidades semanales, pero los registros contables indican que históricamente produce 300, el modelo carece de validez y no debe utilizarse para pronosticar escenarios futuros hasta que no sea recalibrado.

\section{Aplicaciones Empresariales de la Simulación de Eventos Discretos}
La simulación de eventos discretos ha trascendido sus orígenes en la ingeniería militar e industrial para convertirse en una herramienta transversal en la gestión de las organizaciones modernas. Su capacidad para visualizar interdependencias y cuellos de botella la hace invaluable para resolver disyuntivas estratégicas complejas donde la experimentación física es financieramente inviable (Jahangirian et al. 2010).

En la gestión de la cadena de suministro y logística, las empresas utilizan modelos de eventos discretos para evaluar políticas de inventario estocásticas, diseñar la capacidad de almacenamiento de centros de distribución y optimizar las rutas de despacho ante variaciones impredecibles en la demanda (Robinson, 2012). Esto permite simular el efecto bullwhip effect a lo largo de los puntos de la cadena de abastecimiento.

En la manufactura y operaciones, se emplea para diseñar líneas de ensamblaje, determinar la cantidad de los lotes de producción y programar mantenimientos preventivos, es aquí donde se puede introducir una máquina virtual en el modelo para calcular exactamente en cuántos meses se recuperará la inversión gracias a la mitigación de los cuellos de botella (Greasley, 2003).

El sector de servicios (hospitales, sucursales bancarias, aeropuertos,call centers, etc.)  la aplicación principal radica en la gestión del recurso humano y la experiencia del cliente. Las simulaciones permiten dimensionar el número exacto de asesores, cajeros, personal de atención, etc. necesarios para garantizar un nivel de servicio aceptable durante las horas pico, equilibrando el costo laboral con el tiempo de espera tolerado por el usuario final.

% ------------------------------------------------------------------------------
% CAPÍTULO 3
% ------------------------------------------------------------------------------
\chapter{Método de Monte Carlo}

\section{Concepto y Antecedentes del Método de Monte Carlo}
El método de Monte Carlo constituye una de las innovaciones cuantitativas más trascendentales del siglo XX. Sus orígenes se dieron en los años 1940 durante el desarrollo del Proyecto Manhattan, cuando los científicos Stanislaw Ulam y John von Neumann enfrentaron problemas de difusión de neutrones que resultaban matemáticamente imposible mediante ecuaciones analíticas tradicionales. Para sobrepasar este obstáculo, idearon un enfoque basado en el muestreo estadístico aleatorio iterativo. Pero el nombre "Monte Carlo" en sí fue acuñado como una referencia en clave a la famosa ciudad monegasca y sus casinos, dada la naturaleza estocástica del método, equiparable a los juegos de azar (Raychaudhuri, 2008).

Si esto lo trasladamos a un contexto más empresarial, el método de Monte Carlo se comporta como un avance dentro del análisis que permite modelar y analizar sistemas sujetos a riesgo e incertidumbre, reemplazando así las estimaciones puntuales estáticas por distribuciones de probabilidad, siendo así que el hecho de proyectar el Valor Actual Neto (VAN) de un proyecto utilizando un único valor promedio para la demanda o el costo de los insumos, Monte Carlo lo ejecuta miles de escenarios simulados, extrayendo en cada iteración un valor aleatorio diferente para las variables críticas.

No se trata de predecir con exactitud un único futuro, sino delimitar todo el escenario de futuros posibles, siendo de mucha ayuda dentro de la toma de decisiones para los empresarios, un sesgo cognitivo y analítico que asume que el uso de valores medios arrojará un resultado medio exacto. En escenarios complejos con múltiples variables dependientes como independientes, los promedios ignoran la volatilidad real del mercado, ocultando escenarios de riesgo alto que podrían llevar a una organización a la insolvencia (Albright, 2015). Al hacer uso del método de Monte Carlo, la incertidumbre de una variable desconocida en un perfil de riesgo se vuelve cuantificable, facilitando decisiones estratégicas que sigan o consigan aumentar la probabilidad de éxito.

\section{Fundamentos Probabilísticos y Variables Aleatorias}
El método de Monte Carlo es uno de los pilares fundamentales de la teoría de la probabilidad, específicamente la Ley de los Grandes Números y el Teorema del Límite Central. Estos teoremas garantizan que los resultados obtenidos mediante experimentación converjan hacia el comportamiento real del sistema a medida que se incrementa el número de iteraciones (Raychaudhuri, 2008).

Dentro del riesgo empresarial serequiere la definición de variables aleatorias. Una variable aleatoria es una función que asigna un valor numérico a cada posible resultado de una situación incierta. En la modelación financiera y operativa, estas variables se dividen en dos categorías según su naturaleza discreta o continua:

\begin{itemize}
    \item \textbf{Variables aleatorias discretas:} Representan eventos que solo pueden asumir valores enteros o contables. En una simulación administrativa, se utilizan para modelar el número de clientes que ingresan a una tienda en una hora, la cantidad de productos defectuosos en un lote de manufactura o el número de renuncias de personal en un semestre.
    \item \textbf{Variables aleatorias continuas:} Adoptan cualquier valor numérico dentro de un intervalo definido, incluyendo fracciones o decimales infinitos. Son indispensables para simular la fluctuación del tipo de cambio, el rendimiento porcentual de un activo financiero, el peso exacto de la materia prima recibida o el tiempo que demora la ejecución de un proyecto.
\end{itemize}

Dentro de la informática que donde se puede desarrollar el método de Monte Carlo es la generación de números pseudoaleatorios (PRNG, por sus siglas en inglés). Dado que las computadoras operan mediante algoritmos determinísticos, no pueden generar aleatoriedad pura, es por ello que utilizan secuencias matemáticas complejas para producir series numéricas generalmente distribuidas uniformemente entre 0 y 1 que superan estrictas pruebas estadísticas de independencia y uniformidad, tanto que de esa manera estos números actúan como la semilla del azar: cada número pseudoaleatorio generado se transforma, mediante métodos como la transformada inversa, en un valor representativo, señalando un ejemplo podríamos mencionar como convirtiendo un 0.85 en una demanda de 1,200 unidades basada en la distribución histórica de la empresa.

Es imperativo que se comprenda que la confiabilidad del modelo de Monte Carlo depende críticamente de la calidad de la generación aleatoria y del número de iteraciones. Ejecutar 100 escenarios puede arrojar resultados sesgados por la varianza de la muestra; ejecutar 10,000 o 100,000 escenarios garantiza que las colas de la distribución (los eventos extremos y de alto riesgo) sean debidamente exploradas y cuantificadas (Mun, 2006).

\section{Distribuciones de Probabilidad Aplicadas a Monte Carlo}
La selección de cuál va ser con que se va ha desarrollar la distribución de probabilidad adecuada para cada variable de entrada es, sin duda, la decisión más crítica en la construcción de un modelo Monte Carlo, ya que si asignamos una distribución incorrecta por ejemplo, utilizar una curva simétrica para modelar un caso fuertemente sesgado haciendo que pierda la validez de la simulación y deriva en proyecciones engañosas.

A diferencia de la estadística académica básica, donde la distribución normal se aplica por defecto, el análisis de riesgo empresarial exige un catálogo más amplio de curvas estadísticas para reflejar la asimetría y los límites del mundo real (Mun 2006). La Tabla 5 sistematiza las familias de distribuciones probabilísticas más recurrentes en la modelación estocástica, vinculando sus propiedades matemáticas con aplicaciones dentro de un entorno de empresas.

\begin{table}[H]
\centering
\caption{Distribuciones de probabilidad predominantes en simulaciones Monte Carlo empresariales}
\begin{tabular}{p{3.5cm} p{6.5cm} p{5.5cm}}
\toprule
\textbf{Distribución} & \textbf{Características Estadísticas} & \textbf{Aplicación Administrativa} \\
\midrule
Normal & Simétrica y acampanada, definida por su media () y desviación estándar (). Dice que los valores pueden extenderse hacia el infinito. & Tasa de inflación, variaciones de costos operativos estabilizados, errores de medición. \\
Lognormal & Asimétrica con sesgo positivo. Su característica principal es que no admite valores negativos, extendiéndose indefinidamente hacia la derecha. & Modelado de precios de acciones, tasas de interés, valor de bienes raíces, ingresos de nuevos productos. \\
Triangular & Se plantea intuitivamente por tres puntos: el valor mínimo, el más probable (moda) y el máximo. No requiere datos históricos extensos. & Presupuestación inicial, estimación de capacidad de proveedores cuando solo se cuenta con el juicio de expertos. \\
PERT & Similar a la triangular (mínimo, probable, máximo), pero su forma de campana curva concentra mayor probabilidad cerca del valor más probable, reduciendo el peso de los extremos. & Gestión de proyectos, estimación de la duración de tareas críticas, evaluación de cronogramas. \\
Uniforme & Asigna la misma probabilidad de ocurrencia a todos los valores dentro de un rango específico delimitado por un mínimo y un máximo. & Incertidumbre absoluta sobre un insumo (ej. costo futuro de una licencia tecnológica sin histórico previo). \\
\bottomrule
\end{tabular}
\begin{flushleft}
\footnotesize
\textit{Nota.} La elección de la distribución debe validarse preferentemente mediante pruebas de bondad de ajuste si se dispone de datos históricos empíricos. Elaboración propia a partir de los lineamientos de análisis de riesgo de Mun (2006) y Albright and Winston (2015).
\end{flushleft}
\end{table}

Para los tomadores de decisiones, la distribución Triangular y la distribución PERT revisten un interés particular. En el entorno corporativo, la gerencia se enfrenta frecuentemente al lanzamiento de productos disruptivos o a la incursión en nuevos mercados donde no existe un registro histórico de ventas. En estos escenarios de alta incertidumbre, el analista no puede aplicar pruebas de ajuste de parámetros. En su lugar, debe recurrir a la técnica de licitación experta, consultando a los directores comerciales sobre el escenario pesimista, optimista y más probable, y parametrizando el modelo Monte Carlo con base en dichas estimaciones subjetivas pero informadas (Raychaudhuri 2008).

\section{Proceso de Simulación Monte Carlo}
El método de Monte Carlo en las empresas tiene que garantizar la coherencia matemática y la pertinencia administrativa del modelo y evitar modos tradicionales donde el usuario simplemente introduce valores y observa un resultado, la simulación estocástica requiere programar el comportamiento probabilístico en tanto que por ello el proceso estándar para desarrollar una simulación Monte Carlo consta de cinco fases:

\begin{enumerate}
    \item \textbf{Desarrollo del modelo determinístico base:} Se tiene que construir primero un modelo lógico-matemático tradicional, si lo vemos en las finanzas podemos encontrar comúnmente  un flujo de caja descontado para calcular el Valor Actual Neto (VAN); también si vemos otro punto álgido en la parte de la empresa, puede ser una ecuación de cálculo de inventario de seguridad.
    \item \textbf{Identificación de variables críticas (Incertidumbre):} Debemos revisar el modelo base para identificar qué parámetros de entrada están sujetos a volatilidad real y tienen un impacto dentro del caso. No todas las variables deben ser volátiles; la simulación se aplica a factores críticos como la tasa de inflación, el volumen de ventas esperado, el costo de materias primas, etc.
    \item \textbf{Asignación de distribuciones de probabilidad:} Las variables críticas identificadas dejan de ser estimaciones puntuales (valores fijos) y deberán ser reemplazadas por distribuciones de probabilidad aquí ya tenemos algunas conocidas como la Normal, Triangular o PERT, estas deberán ser aplicada según corresponda la característica de las variables críticas preferentemente en datos históricos o, en su defecto, en la observación de expertos .
    \item \textbf{Ejecución iterativa y muestreo aleatorio:} En cada iteración, el software genera números pseudoaleatorios ya que este no puede generar al 100\% la aleatoriedad y extrae un valor de cada distribución asignada y así se origina el modelo completo. Este proceso se repite miles de veces (típicamente entre 10,000 y 100,000 iteraciones) para garantizar la confiabilidad estadística mediante la Ley de los Grandes Números.
    \item \textbf{Consolidación estadística de los resultados:} Cuando finalice las iteraciones, el software agrupa los miles de resultados generados en una única distribución de frecuencias (histograma de salida), la cual representa el perfil de riesgo integral del evento evaluado.
\end{enumerate}

Este proceso transforma un escenario simplista de escenario único donde se ocasionan sesgos de optimismo en una herramienta capaz de evaluar escenarios de sensibilidad, de esta manera proporcionando un mapa completo de los futuros posibles que se puede ocasionar.

\section{Análisis e Interpretación de Resultados}
La simulación Monte Carlo no entrega una respuesta única o determinística, sino un panorama estadístico, es aquí donde podemos no con la certeza absoluta pero sí con probabilidades tener parámetros que nos ayuden a gestionar mejor la toma de decisiones, es por ello que es crucial y muy importante la correcta interpretación de las salidas del modelo es la etapa donde el análisis cuantitativo.

El resultado es un histograma de frecuencias relativas, acompañado de una curva de probabilidad acumulada. De esta gráfica se extraen métricas fundamentales que la gerencia utiliza para medir el riesgo de una decisión. La Tabla 6 sintetiza los indicadores de salida más relevantes y su aplicación administrativa.

\begin{table}[H]
\centering
\caption{Métricas probabilísticas de salida y su interpretación gerencial}
\begin{tabular}{p{4cm} p{6cm} p{5.5cm}}
\toprule
\textbf{Métrica Estadística} & \textbf{Definición Cuantitativa} & \textbf{Pregunta de Negocio que Responde} \\
\midrule
Valor Esperado (Media) & Promedio aritmético de todos los resultados simulados. Suele diferir del resultado del modelo determinístico estático debido a la asimetría del riesgo. & ¿Cuál es el resultado más representativo a largo plazo si la decisión se repitiera bajo condiciones idénticas? \\
Probabilidad de Éxito / Fracaso & Porcentaje de iteraciones que cumplen con un umbral crítico (ej. iteraciones donde el VAN es mayor a cero). & ¿Qué probabilidad exacta tenemos de destruir valor para los accionistas si aprobamos este proyecto? \\
Percentiles (P5 y P95) & Valores límite que encierran el 90\% de los escenarios centrales. El P5 representa el peor escenario probable y el P95 el mejor. & ¿Cuál es la máxima pérdida financiera a la que nos exponemos con un 95\% de nivel de confianza? \\
Valor en Riesgo (VaR) & Medida estandarizada que cuantifica la pérdida máxima esperada en un horizonte de tiempo y nivel de confianza determinados. & ¿Cuánto capital de contingencia debemos inmovilizar para absorber choques de mercado imprevistos? \\
\bottomrule
\end{tabular}
\begin{flushleft}
\footnotesize
\textit{Nota.} Elaboración propia a partir de los fundamentos de cuantificación de riesgo de Mun (2006) y Vose (2008).
\end{flushleft}
\end{table}

Interpretar correctamente los percentiles permite a las empresas abandonar la planificación basada en escenarios subjetivos (optimista, base, pesimista) e implementar una gestión de riesgos basada en niveles de confianza matemáticos, protegiendo así el patrimonio de la organización.

\section{Análisis de Sensibilidad y Riesgo}
Una vez que la gerencia ha cuantificado el riesgo global de un proyecto mediante el método de Monte Carlo, el siguiente paso estratégico es identificar el origen anatómico de dicho riesgo. El análisis de sensibilidad es la técnica cuantitativa encargada de medir qué proporción de la varianza en el resultado final es atribuible a cada variable de entrada individual (Vose, 2008).

Computacionalmente, este análisis se realiza calculando los coeficientes de correlación de rango (como el coeficiente de Spearman) entre las variables estocásticas de entrada y la variable de salida durante las iteraciones de la simulación. El resultado se visualiza típicamente a través de un "gráfico de tornado", el cual clasifica las variables de mayor a menor impacto en la rentabilidad o eficiencia del sistema (Mun, 2006).

El análisis de sensibilidad cambia drásticamente la forma en que se ejecutan las estrategias de mitigación de riesgos. Si una empresa determina que su proyecto de expansión tiene un 35\% de probabilidad de arrojar pérdidas, la intuición tradicional sugeriría recortar todos los presupuestos de manera lineal, el análisis de sensibilidad estocástico puede revelar que el 80\% de la varianza del proyecto depende exclusivamente del costo del acero, mientras que los costos laborales tienen un impacto marginal, es conveniencia de esto se debe enfocar sus recursos de mitigación en negociar contratos de cobertura de precios.

El análisis de sensibilidad y riesgo derivado de Monte Carlo optimiza la asignación de recursos para las empresas, permitiendo a los jefes invertir tiempo y capital en controlar exclusivamente las variables que realmente amenazan la viabilidad de la estrategia.

\section{Aplicaciones Empresariales del Método de Monte Carlo}
El método de Monte Carlo ha ocasionado que casi todas las áreas de una empresa moderna, puedan optar a este método como el estándar analítico para la evaluación de decisiones bajo incertidumbre. Su versatilidad le permite adaptarse tanto a problemas financieros de alta complejidad como a dilemas de financiamiento (Raychaudhuri, 2008).

La evaluación financiera con Monte Carlo es utilizada para modelar opciones reales, valorar empresas y estructurar portafolios de inversión. Sustituye la Tasa Interna de Retorno (TIR) estática por una distribución de TIRs probables, permitiendo a los comités de inversión visualizar el perfil de riesgo retorno antes de autorizar adquisiciones corporativas millonarias o proyectos de infraestructura de largo plazo (Mun, 2006).

La simulación supera las severas limitaciones del método CPM/PERT clásico (Kwak, 2007). Como demuestran los cálculos de la ruta crítica es engañoso porque ignora el "sesgo de convergencia" cuando múltiples tareas paralelas se retrasan simultáneamente. Al aplicar Monte Carlo al cronograma del proyecto, el software simula miles de duraciones posibles para cada actividad, determinando con precisión la probabilidad real de entregar el proyecto en la fecha estipulada y calculando las reservas de contingencia (en tiempo y presupuesto) necesarias para evitar penalizaciones contractuales.

% ------------------------------------------------------------------------------
% CAPÍTULO 4
% ------------------------------------------------------------------------------
\chapter{Integración de Eventos Discretos y Monte Carlo}

\section{Simulación de Eventos Discretos y Monte Carlo: puntos de encuentro y divergencias}
Los eventos discretos y el enfoque de Monte Carlo casi siempre aparecen retratados como senderos independientes, ambas herramientas comparten una misma raíz conceptual: el rechazo al determinismo de los cálculos promedios simples. La SED y el Monte Carlo se sostienen sobre un análisis estocástico que depende, en lo fundamental, de la producción de números pseudoaleatorios y de la extracción reiterada de valores desde funciones de probabilidad. Es justamente mediante estos recursos que logran representar la volatilidad característica del contexto organizacional. Hay otro punto de contacto relevante: los dos métodos exigen un volumen considerable de corridas de iteraciones para que las estimaciones obtenidas tenga de respaldo estadístico firme, algo que se desprende directamente del principio de los grandes números (Law, 2015).

Ahora bien, las discrepancias que las separan son sustanciales y terminan por delimitar la clase de situaciones que cada una puede resolver de manera autónoma. El factor que verdaderamente las distancia es la postura que adoptan frente al paso del tiempo y los vínculos de dependencia entre elementos. Por un lado, la simulación discreta trabaja con una lógica evolutiva y encadenada; lo que persigue es acompañar el recorrido horario de piezas, clientes o transacciones que pugnan por acceder a medios escasos, lo cual permite detectar congestiones y demoras. Por otro lado, la propuesta tradicional de Monte Carlo opera sin reloj interno, en un plano fijo. Su tarea consiste en sopesar el peligro conjunto de una operación o proyecto, analizando magnitudes sometidas a variación en un punto concreto del tiempo o a lo largo de un lapso ya cerrado, pero sin reparar en el orden ni en la interacción de las actividades que lo componen (Banks et al., 2014).

La Tabla 7 condensa estos contrastes y funciona como una matriz orientadora para decantarse por una u otra alternativa en función del tipo de encrucijada directiva que se deba enfrentar.

\begin{table}[H]
\centering
\caption{Contraste entre Simulación de Eventos Discretos y Método de Monte Carlo}
\begin{tabular}{p{4cm} p{5.5cm} p{5.5cm}}
\toprule
\textbf{Dimensión de análisis} & \textbf{Simulación de Eventos Discretos} & \textbf{Método de Monte Carlo} \\
\midrule
Tratamiento del tiempo & Progresivo. El cronómetro interno constituye el núcleo articulador del experimento. & Inmóvil. La variable temporal queda fuera de la mecánica de cálculo. \\
Foco de atención & Conexiones y dependencias del proceso, aprovechamiento de medios y desplazamiento de flujos. & Variabilidad de los parámetros, exposición económica y frecuencia de sucesos. \\
Manejo de la información & Persigue la trayectoria completa de cada elemento individual que atraviesa el sistema. & Realiza un examen global del conjunto apoyándose en un muestreo intensivo de escenarios. \\
Indicadores resultantes & Plazos de espera, tasas de ocupación, volumen de salida, tamaño de las filas. & Rendimiento esperado, Valor en Riesgo (VaR), percentiles de pérdida, probabilidad de quiebre. \\
\bottomrule
\end{tabular}
\begin{flushleft}
\footnotesize
\textit{Nota.} Elaboración propia con base en los esquemas clasificatorios desarrollados por Law (2015) y Rubinstein y Kroese (2016).
\end{flushleft}
\end{table}

\section{Complementariedad entre Eventos Discretos y Monte Carlo}
A pesar de que la simulación de eventos discretos y el método de Monte Carlo utilizan diferentes formas de análisis, esto no quiere decir que sean métodos excluyentes. Por el contrario, ambos pueden complementarse y utilizarse de manera conjunta para realizar un análisis más completo. En una empresa, los problemas en la planificación estratégica pueden aparecer cuando la gerencia analiza los riesgos financieros sin considerar las limitaciones que existen en las operaciones. También puede ocurrir lo contrario, cuando se busca mejorar los procesos suponiendo que las condiciones económicas se mantendrán estables (Robinson 2014).

La complementariedad entre estos dos métodos se puede entender a partir de los llamados "puntos ciegos". El método de Monte Carlo es muy útil para analizar el "qué", ya que permite estudiar diferentes situaciones que podrían presentarse, como el nivel de demanda que tendrá una empresa, el posible aumento del precio de los insumos o el efecto de la inflación en los costos. Sin embargo, este método por sí solo tiene algunas limitaciones para explicar el "cómo" ocurrirán estas situaciones en la práctica. Por ejemplo, no permite conocer con el mismo nivel de detalle qué pasaría con una planta de producción si la demanda aumenta demasiado en una sola semana o si los pedidos superan la capacidad de atención de la empresa. En estos casos, la simulación de eventos discretos resulta importante, porque permite analizar cómo funcionan los procesos y comprobar si las proyecciones obtenidas mediante Monte Carlo pueden ser atendidas teniendo en cuenta la capacidad actual de la empresa (Jahangirian et al. 2010).

El uso conjunto de ambas técnicas permite realizar un análisis más completo de la organización y de los posibles riesgos que puede enfrentar. Monte Carlo ayuda a estudiar los cambios e incertidumbres que pueden presentarse, mientras que la simulación de eventos discretos permite observar cómo responderían las operaciones ante estas situaciones. Al combinar los resultados de ambos métodos, se puede obtener una representación más cercana a la realidad de la empresa, similar a lo que se conoce como un "gemelo digital" integral de la organización.Monte Carlo simula el entorno externo y su volatilidad, mientras que la SED simula el entorno interno y sus restricciones físicas.

\section{Integración de Ambas Técnicas para el Análisis de Escenarios}
La integración técnica de ambas metodologías requiere una arquitectura computacional avanzada, comúnmente denominada "simulación anidada" (nested simulation) o modelado híbrido. El propósito de esta integración es someter el modelo de procesos a la volatilidad del entorno empresarial, generando escenarios de estrés multidimensionales (Rubinstein and Kroese 2016).

En la práctica cuantitativa, esta integración se estructura típicamente colocando el modelo de Monte Carlo como un "envoltorio" (wrapper) alrededor del modelo de eventos discretos. El proceso lógico opera de la siguiente manera:

\begin{enumerate}
    \item \textbf{Muestreo externo (Monte Carlo):} El algoritmo maestro selecciona aleatoriamente valores macroeconómicos o de demanda global a partir de distribuciones probabilísticas (ej. volumen total de pedidos para el mes, tasa de ausentismo del personal, costo logístico unitario).
    \item \textbf{Ejecución interna (Eventos Discretos):} Estos valores paramétricos se inyectan como variables de entrada en el modelo operativo, así ejecuta entonces la dinámica cronológica del mes completo, procesando entidades, gestionando colas, enfrentando averías,etc. todo bajo las condiciones límite que proporcionada por el muestreo externo.
    \item \textbf{Extracción del resultado consolidado:} Al finalizar el tiempo simulado, se extraen los costos operativos reales y los niveles de servicio generados en ese escenario específico.
    \item \textbf{Iteración masiva:} El ciclo se repite miles de veces.
\end{enumerate}

Esta integración no es una medida aislada, sino una distribución de probabilidad de los KPIs operativos. La gerencia no solo descubre que el tiempo promedio de entrega es de tres días, sino que puede afirmar con rigor estadístico: "Existe un 95% de probabilidad de cumplir con las entregas en menos de cuatro días, considerando simultáneamente la volatilidad de la demanda externa y los cuellos de botella internos" (Kelton et al. 2015).

\section{Aplicación Conjunta en la Toma de Decisiones Empresariales}
La aplicación conjunta de SED y Monte Carlo eleva drásticamente la calidad de las decisiones estratégicas de alta dirección, especialmente en las áreas de presupuestación de capital (capital budgeting) y diseño de resiliencia operativa.

Un caso paradigmático de esta aplicación conjunta ocurre en la evaluación de proyectos de infraestructura, como la construcción de un nuevo centro de distribución. n una evaluación tradicional, el Valor Actual Neto (VAN) de un proyecto suele calcularse utilizando valores estimados y condiciones que se consideran relativamente estables. Sin embargo, al utilizar de manera conjunta la simulación de eventos discretos y el método de Monte Carlo, es posible analizar diferentes factores que pueden afectar los resultados de un proyecto. Monte Carlo permite simular cambios en aspectos como las tasas de interés, los costos de construcción y el crecimiento de la demanda a lo largo del tiempo. Al mismo tiempo, la simulación de eventos discretos permite analizar si los recursos y la capacidad disponible pueden responder adecuadamente ante los diferentes niveles de demanda que se presentan en cada escenario (Mun 2006).

Por ejemplo, si el modelo integrado muestra que en el 30\% de los escenarios donde se presenta una demanda alta, los vehículos deben esperar más de cinco horas para ser atendidos, se puede identificar que existe una limitación en la capacidad del proceso. Esto significa que, aunque los resultados financieros indiquen que el proyecto puede ser rentable, en la práctica podrían presentarse dificultades que afecten los ingresos esperados. Ante esta situación, la decisión ya no se limita solamente a aprobar o rechazar el proyecto. En cambio, se pueden realizar modificaciones antes de su puesta en marcha, como aumentar los recursos disponibles, reorganizar los espacios o mejorar la distribución de las actividades. De esta manera, la combinación de ambos métodos permite tomar decisiones más completas y reducir los posibles problemas que podrían afectar los resultados finales del proyecto.

\section{Ventajas y Limitaciones de su Aplicación Integrada}
La combinación de la simulación de eventos discretos y el método de Monte Carlo permite ampliar la forma en que se analizan los problemas y se toman decisiones. Sin embargo, utilizar ambos métodos al mismo tiempo también implica ciertas dificultades que deben ser consideradas antes de su aplicación. No basta con contar con herramientas de análisis avanzadas, sino que también es necesario conocer sus alcances y limitaciones para evitar resultados que no representen correctamente una situación real (Sargent, 2013).

Entre los principales beneficios se encuentra la posibilidad de analizar diferentes factores de manera conjunta. Monte Carlo permite estudiar la incertidumbre relacionada con variables que pueden cambiar con el tiempo, mientras que la simulación de eventos discretos ayuda a observar cómo estas variaciones pueden afectar el funcionamiento de un proceso. Al reunir ambos análisis, se obtiene una visión más amplia de los posibles resultados y se pueden identificar problemas que quizás no serían visibles al utilizar solamente uno de los métodos. Esto también ayuda a reducir el exceso de confianza al momento de tomar una decisión, ya que permite considerar situaciones favorables y desfavorables antes de actuar.

A pesar de estas ventajas, también existen algunas dificultades. Una de ellas es el tiempo y los recursos necesarios para realizar las simulaciones. Por ejemplo, ejecutar miles de escenarios mediante Monte Carlo puede realizarse en poco tiempo, pero si cada uno de esos escenarios debe pasar por un modelo detallado de eventos discretos, el proceso puede volverse mucho más lento y requerir una mayor capacidad de procesamiento.

Otro aspecto importante es la correcta relación entre las variables utilizadas en el modelo. En una situación real, muchas variables no funcionan de manera independiente. Por ejemplo, un aumento en el precio del combustible puede generar un incremento en los costos y, al mismo tiempo, provocar una reducción en la demanda o en la cantidad de actividades realizadas. Si esta relación no se considera correcta, el modelo puede generar situaciones poco realistas y llevar a conclusiones equivocadas (Rubinstein, 2016).

Por esta razón, la aplicación conjunta de ambos métodos requiere una adecuada planificación y conocimientos en diferentes áreas. Es necesario comprender los principios estadísticos, conocer el funcionamiento de los procesos que se desean analizar y, además, tener la capacidad de interpretar los resultados obtenidos. Cuando estos elementos se integran correctamente, la simulación puede convertirse en una herramienta útil para evaluar diferentes alternativas y tomar decisiones con una mayor cantidad de información.

% ------------------------------------------------------------------------------
% CAPÍTULO 5
% ------------------------------------------------------------------------------
\chapter{Herramientas y Metodología de Simulación}

\section{Etapas para Desarrollar un Modelo de Simulación}
Desarrollar un modelo de simulación sin una planificación metódica suele derivar en lo que la ingeniería de sistemas denomina "modelos huérfanos": programas computacionalmente correctos, pero administrativamente inútiles por no responder a las necesidades reales de los tomadores de decisiones (Robinson, 2014).

Para evitar este sesgo técnico, la investigación de operaciones establece un ciclo de vida estandarizado para los proyectos de simulación. Siguiendo los preceptos de Law (2015) y adaptándolos al entorno corporativo, el proceso se divide en las siguientes etapas iterativas:

\begin{enumerate}
    \item \textbf{Definición del problema y formulación de objetivos:} Constituye la fase de alineación estratégica. El analista cuantitativo y la gerencia deben acordar qué sistema se va a estudiar, cuáles son los límites de dicho sistema (alcance) y qué indicadores clave de desempeño (KPIs) dictarán el éxito o fracaso de las alternativas.
    \item \textbf{Diseño del modelo conceptual y recolección de datos:} Antes de escribir cualquier línea de código, el sistema físico se abstrae en diagramas de flujo y mapas lógicos. Paralelamente, se recolectan los datos históricos (tiempos de atención, demanda, costos) y se someten a pruebas estadísticas de bondad de ajuste para parametrizar las distribuciones de probabilidad de las variables estocásticas.
    \item \textbf{Traducción al modelo computacional:} El modelo conceptual se codifica utilizando un lenguaje de programación (como Python) o software especializado. La elección de la herramienta en esta etapa está condicionada por la naturaleza discreta o estática del problema y el presupuesto del proyecto.
    \item \textbf{Verificación y Validación (V\&V):} Como se discutió en capítulos anteriores, la verificación asegura que el software esté libre de errores lógicos (bugs), mientras que la validación —mediante la Prueba de Turing o análisis de sensibilidad históricos— garantiza que el modelo imite con precisión el comportamiento del negocio real (Sargent 2013).
    \item \textbf{Diseño de experimentos y ejecución:} Dentro del software se implementa los escenarios propuestos puede ser por ejemplo, "aumentar la capacidad del almacén en un 20\%". Se determina el número adecuado de iteraciones para que los resultados alcanzan significancia estadística y se ejecutan las simulaciones.
    \item \textbf{Análisis de salidas e implementación:} Los datos que salen de la simulación que arrojan como resultado se transforman en intervalos de confianza, y aquí ya se podría realizar la redacción para poder documentar los hallazgos en un informe que justifica cuantitativamente la selección de la alternativa óptima, facilitando su adopción en la realidad operativa.
\end{enumerate}

\section{Python y la Simulación de Eventos Discretos}
Con el avance de la informática, actualmente es mucho más fácil acceder a herramientas que permiten realizar modelos y simulaciones de mayor complejidad. Hace algunos años, la simulación de eventos discretos dependía principalmente de programas comerciales que tenían costos elevados, como Arena o FlexSim. Estos programas facilitaban la construcción de modelos mediante interfaces gráficas, aunque en algunos casos presentaban ciertas limitaciones cuando se necesitaba conectarlos con otras herramientas o modificar su funcionamiento de acuerdo a necesidades específicas (Dagkakis, 2016).

En los últimos años, los lenguajes de programación han cambiado esta situación, especialmente Python, que se ha convertido en una herramienta muy utilizada para trabajar con datos y realizar diferentes tipos de análisis. Una de las razones de su popularidad es que su sintaxis resulta relativamente sencilla y además cuenta con una gran cantidad de recursos disponibles en internet. También existe una comunidad bastante amplia que desarrolla y comparte nuevas herramientas para diferentes necesidades.

Para realizar simulaciones de eventos discretos utilizando Python, una de las bibliotecas más conocidas es SimPy. Esta herramienta permite construir modelos mediante código y representar procesos que ocurren en diferentes momentos. A diferencia de programas como Arena o FlexSim, SimPy no funciona como un programa independiente con una interfaz gráfica donde se colocan elementos visualmente. Más bien, utiliza las funciones y características propias de Python para representar los procesos y eventos que se desean estudiar (Dagkakis, 2016).

Una de las principales ventajas de trabajar con Python y SimPy es la libertad que ofrece para construir los modelos. El usuario no depende solamente de elementos que ya vienen preparados en un programa, sino que puede crear sus propias reglas según las características del problema. Por ejemplo, se podría desarrollar un modelo que determine el orden de atención de diferentes personas según ciertos criterios y que este orden puede cambiar conforme aparecen nuevos datos. Este tipo de situaciones puede resultar más complicado de representar cuando se trabaja únicamente con programas que tienen una estructura más cerrada.

Otra ventaja importante es la posibilidad de trabajar con información proveniente de diferentes fuentes. Python cuenta con bibliotecas como Pandas, que permite organizar y procesar grandes cantidades de datos, y NumPy, que facilita el trabajo con cálculos y operaciones matemáticas. Estos datos pueden ser utilizados posteriormente en una simulación realizada con SimPy y los resultados pueden representarse mediante gráficos utilizando herramientas como Matplotlib,se puede seguir un proceso que va desde la recopilación y análisis de los datos hasta la simulación y visualización de los resultados.

El uso de herramientas de código abierto representa una alternativa accesible para quienes no cuentan con un presupuesto elevado para adquirir licencias de programas especializados. Al utilizar Python y sus diferentes bibliotecas, es posible desarrollar modelos de simulación sin tener que realizar grandes inversiones en software. Esto facilita que estudiantes, investigadores y pequeñas organizaciones puedan experimentar con este tipo de herramientas y aplicarlas en diferentes problemas, aunque también es necesario contar con los conocimientos necesarios para programar y construir correctamente el modelo financiera permite implementar analítica avanzada sin comprometer el presupuesto de capital.

Sin embargo, el uso de Python también presenta limitaciones gerenciales. Su adopción requiere que el administrador o el analista posea competencias sólidas en programación orientada a objetos. Además, carece de las potentes animaciones 3D nativas que ofrecen los softwares comerciales, ojeadas que en ocasiones dificultan la comunicación visual de los resultados operativos a la alta dirección, quienes suelen preferir visualizar el flujo físico de la fábrica antes de aprobar inversiones millonarias.

\section{Excel y el Modelamiento Probabilístico}
A pesar del auge de los lenguajes de programación avanzados y del software especializado, las hojas de cálculo continúan siendo la herramienta analítica más difundida en el entorno corporativo. Microsoft Excel se mantiene como el estándar operativo para la gestión de datos financieros y administrativos en las pequeñas, medianas y grandes empresas, debido a su accesibilidad, su baja curva de aprendizaje y su capacidad para vincularse de manera directa con bases de datos comerciales.

Excel posee una arquitectura idónea para desarrollar modelos determinísticos y sirve como la plataforma base para el modelamiento probabilístico. Mediante el uso de funciones matemáticas y estadísticas nativas (como BUSCARV, COINCIDIR, SI, PROMEDIO, o funciones de distribución como DISTR.NORM.N), los analistas pueden estructurar hojas de trabajo dinámicas que calculen flujos de caja, amortizaciones o proyecciones de inventario. Pero eso ya no es suficiente al momento de enfrentarse a la incertidumbre, la hoja de cálculo tradicional presenta una limitación crítica: el análisis estático de escenarios de "qué pasaría si..." (What-If Analysis), mediante herramientas como el Administrador de Escenarios o las Tablas de Datos, suele restringirse a un número limitado de combinaciones predefinidas, ignorando por completo la probabilidad de múltiples eventos sucesos que pueden ocurrir (Albright, 2015).

Para superar esta limitación que tenemos con el programa de Excel en un entorno de simulación, se complementa mediante la generación de variables aleatorias a partir de funciones como ALEATORIO() (RAND()), que produce valores uniformes entre 0 y 1, o ALEATORIO.BETWEEN() para rangos enteros. Estas funciones permiten simular de forma rudimentaria escenarios de Monte Carlo utilizando las fórmulas de transformación de la inversa de la distribución acumulada. Sin embargo, cuando se requiere evaluar modelos complejos con decenas de variables estocásticas interdependientes, la programación manual de miles de iteraciones mediante macros de Visual Basic para Aplicaciones (VBA) se vuelve computacionalmente ineficiente y propensa a errores lógicos.

Por consiguiente, en la práctica administrativa, Excel actúa principalmente como el repositorio estructurado de datos históricos y como la interfaz lógica donde reside el modelo determinístico base, el cual posteriormente es parametrizado y ejecutado mediante complementos especializados de simulación de riesgos (Mun 2006).

\section{Crystal Ball y la Simulación Monte Carlo}
Para dotar a las hojas de cálculo tradicionales de verdadera capacidad estocástica sin necesidad de desarrollar código informático complejo, la industria del análisis cuantitativo ha adoptado complementos de software especializados, siendo Oracle Crystal Ball una de las plataformas corporativas más robustas para la ejecución del método de Monte Carlo.

Crystal Ball opera directamente como un complemento (add-in) integrado en Microsoft Excel. Su arquitectura analítica transforma las celdas estáticas de la hoja de cálculo en un entorno dinámico de evaluación de riesgos mediante la definición de tres componentes fundamentales (Albright and Winston 2015):

\begin{itemize}
    \item \textbf{Supuestos (Assumptions):} Son las celdas de entrada del modelo que contienen incertidumbre. El analista selecciona la celda correspondiente (por ejemplo, el costo unitario de insumos o el volumen de ventas) y le asigna una distribución de probabilidad (Normal, Triangular, Lognormal, Uniforme, entre otras) utilizando una interfaz gráfica guiada.
    \item \textbf{Pronósticos (Forecasts):} Son las celdas de salida o celdas objetivo del modelo (como el Valor Actual Neto - VAN, la Tasa Interna de Retorno - TIR, o el costo total operativo) cuyas fluctuaciones se desea medir y registrar tras la ejecución de las simulaciones realizadas en diversos escenario.
    \item \textbf{Preferencias de ejecución (Run Preferences):} Configuran el comportamiento de las variaciones de los escenarios, permitiendo establecer el número exacto de iteraciones (por ejemplo, 10,000 escenarios), el nivel de precisión estadística deseado y la gestión de la aleatoriadad para garantizar la reproducibilidad de los experimentos.
\end{itemize}

Otra herramienta muy importante es el complemento de excel llamado Crystal Ball que aporta un valor analítico incalculable al generar informes estadísticos automatizados que incluyen histogramas de frecuencia, curvas de probabilidad acumulada y análisis de sensibilidad instantáneos mediante gráficos, y si no requiere conocimientos avanzados de programación, permite que sea una alternativa tecnológica para los analfabetos tecnológicos, facilitando la justificación de inversiones complejas bajo condiciones de alta volatilidad de mercado.

\section{Comparación y Selección de Herramientas}
La existencia de múltiples herramientas desde lenguajes de programación abiertos hasta complementos de hojas de cálculo y software comercial de propósito específico, es necesario que el encargado de la gerencia correspondiente ejecute un proceso de selección fundamentado en criterios técnicos, económicos y operativos. Escoger la plataforma incorrecta puede comprometer el cronograma del proyecto analítico, generar costos innecesarios de licenciamiento o restringir la complejidad del modelo a desarrollar.

Para estructurar este análisis de selección, la Tabla 8 sintetiza las características operativas, las ventajas y el contexto administrativo ideal de las principales herramientas abordadas en la literatura de investigación de operaciones.

\begin{table}[H]
\centering
\caption{Comparación de herramientas computacionales para la simulación empresarial}
\begin{tabular}{p{3.5cm} p{4cm} p{4cm} p{4cm}}
\toprule
\textbf{Herramienta} & \textbf{Arquitectura y Enfoque} & \textbf{Ventajas Principales} & \textbf{Contexto Administrativo Ideal} \\
\midrule
Python / SimPy & Lenguaje de programación de propósito general orientado a eventos discretos. & Alta flexibilidad algorítmica, integración con bases de datos y costo cero (Open Source). & Organizaciones con capacidad técnica interna, análisis masivos de datos y procesos hiper-personalizados. \\
Excel + Crystal Ball & Complemento estocástico integrado en hojas de cálculo para simulación Monte Carlo. & Curva de aprendizaje rápida, interfaz intuitiva y uso directo de modelos financieros existentes. & Evaluación de proyectos, finanzas corporativas, análisis de riesgo de inversión y gestión MYPE. \\
Software Comercial (Ej. Arena / FlexSim) & Plataformas propietarias basadas en componentes visuales de arrastrar y soltar (drag-and-drop). & Potentes animaciones 3D nativas, módulos especializados para manufactura y soporte técnico corporativo. & Grandes corporaciones industriales, diseño de plantas de producción y presentación de proyectos a directorios ejecutivos. \\
\bottomrule
\end{tabular}
\begin{flushleft}
\footnotesize
\textit{Nota.} Elaboración propia a partir de los criterios de evaluación de software de Dagkakis and Heavey (2016) and Albright and Winston (2015).
\end{flushleft}
\end{table}

La decisión de adopción tecnológica debe basarse en un balance riguroso entre la complejidad analítica del problema y los recursos disponibles en la organización. Mientras que un problema de eventos discretos con flujos lógicos altamente personalizados justificará la inversión en tiempo para programar en Python, una evaluación de riesgo financiero sobre un flujo de caja requerirá la agilidad analítica de Crystal Ball (Mun 2006; Dagkakis and Heavey 2016). Alinear las capacidades del software con los objetivos estratégicos es necesario para asegurar que la tecnología sea un medio eficiente para la reducción de la incertidumbre y no un fin en sí mismo.

% ------------------------------------------------------------------------------
% CAPÍTULO 6
% ------------------------------------------------------------------------------
\chapter{Aplicación Práctica para la Toma de Decisiones}

\section{Descripción del Caso Empresarial}
Para analizar el problema, se toma como referencia un centro de distribución regional encargado de recibir y enviar diferentes tipos de mercancías. En los últimos meses, el aumento de las actividades ha generado dificultades principalmente en las zonas donde se realizan las operaciones de carga y descarga. La cantidad de vehículos que llegan al lugar no siempre es la misma y en los momentos donde existe mayor movimiento, la capacidad disponible ya no resulta suficiente para atenderlos con rapidez.

El funcionamiento actual depende de una cantidad determinada de montacargas y de trabajadores encargados de realizar la descarga de los vehículos. Cuando llegan varios camiones casi al mismo tiempo, algunos tienen que esperar hasta que exista personal o equipos disponibles para poder ser atendidos. Esta situación se vuelve más complicada en las temporadas donde aumenta la cantidad de mercancías que deben ser recibidas. Como consecuencia, los tiempos de espera pueden aumentar bastante, generando retrasos, posibles pagos por incumplimientos y pérdidas relacionadas con los vehículos que permanecen sin poder continuar con sus actividades. También se producen problemas de espacio y mayor acumulación de vehículos en las zonas exteriores.

Ante esta situación, se han planteado dos posibles opciones para mejorar el funcionamiento del centro de distribución. La primera alternativa consiste en aumentar la capacidad de las instalaciones. Para esto se propone construir dos nuevos espacios destinados a la carga y descarga, además de incorporar nuevos trabajadores. Esta opción requiere una inversión considerable, pero se espera que permita atender una mayor cantidad de vehículos y reducir los tiempos de espera.

La segunda alternativa busca mejorar el proceso sin realizar una ampliación importante de las instalaciones. En este caso, se plantea mantener los espacios actuales e incorporar un sistema que permita organizar mejor los turnos de atención. También se considera adquirir un montacargas con mayor capacidad, lo cual tendría un costo menor en comparación con la primera opción.

Para decidir entre estas dos propuestas, no sería suficiente utilizar solamente los valores promedio de los costos o de la cantidad de vehículos que llegan. Las condiciones pueden cambiar de un día a otro y esto puede afectar el resultado final de cada alternativa. Por este motivo, se propone desarrollar un modelo que combine dos métodos de simulación. La simulación de eventos discretos permitirá observar cómo se comportan las esperas y la atención de los vehículos, mientras que Monte Carlo ayudará a representar diferentes posibles cambios en los costos y en la demanda.

Con los resultados obtenidos se podrá comparar el comportamiento de las dos alternativas bajo diferentes situaciones. De esta manera, será posible determinar cuál de las opciones presenta mejores resultados y cuál puede ofrecer una mayor estabilidad para el funcionamiento del centro de distribución, considerando no solo la inversión inicial, sino también los posibles costos y problemas que puedan aparecer en el futuro.

\section{Identificación y Análisis de las Variables del Sistema}
El primer paso metodológico en la construcción del modelo consiste en auditar el sistema logístico para aislar los parámetros determinísticos de aquellos sujetos a incertidumbre. La recolección de datos históricos y su posterior análisis estadístico permiten parametrizar el comportamiento operativo del centro de distribución (Law 2015).

Las variables del sistema se clasifican en dos grandes grupos para su modelamiento cuantitativo:

\begin{itemize}
    \item \textbf{Variables de Entrada Estocásticas (Incertidumbre):}
    \begin{itemize}
        \item Intervalo de llegada de los camiones: Modelado mediante una distribución Exponencial, reflejando la independencia estadística entre la llegada de los transportistas, con una media () variable según las estaciones del año.
        \item Tiempo de servicio o descarga: Parametrizado a través de una distribución PERT o Triangular, estableciendo un tiempo mínimo, un valor más probable y un tiempo máximo condicionado por el volumen de carga transportada por unidad.
        \item Costo operativo por hora de retraso y penalizaciones: Variable financiera sujeta a la volatilidad del mercado logístico, modelada con una distribución Lognormal.
    \end{itemize}
    \item \textbf{Variables de Decisión y Estado (Controlables):}
    \begin{itemize}
        \item Número de andenes activos (c): Parámetro estructural sujeto a modificación (evaluación entre la capacidad actual y la Alternativa A).
        \item Capacidad de la cola de espera: Limitada por el espacio físico del patio de maniobras.
        \item Nivel de utilización de los recursos: Porcentaje de ocupación del personal de cuadrilla y de los equipos de elevación.
    \end{itemize}
\end{itemize}

La correcta identificación de estas variables asegura que el modelo computacional no sea una representación abstracta, sino un reflejo fiel de las restricciones operativas y financieras que condicionan la toma de decisiones en la empresa (Banks et al. 2014).

\section{Construcción del Modelo de Eventos Discretos}
Luego de definir los datos que se van a utilizar y conocer el comportamiento de las variables, se empieza a construir el modelo de simulación. Para este caso, el funcionamiento puede entenderse de una manera sencilla: los camiones llegan al centro de distribución, esperan cuando no existe un espacio disponible y posteriormente pasan a ser atendidos. Los lugares donde se realiza la descarga funcionan como puntos de atención y los trabajadores junto con los equipos disponibles son los recursos necesarios para realizar esta actividad.

El funcionamiento del modelo se basa en registrar los cambios que van ocurriendo con el paso del tiempo. Cada llegada o salida de un camión representa un cambio en el sistema y genera una nueva situación. Para representar este proceso se consideran las siguientes acciones principales:

Ingreso de los camiones: Los vehículos van llegando en diferentes momentos y el tiempo entre una llegada y otra es generado de acuerdo con los valores establecidos para el modelo. Si existe un espacio disponible para realizar la descarga, el camión puede ser atendido de forma inmediata. Cuando todos los espacios están ocupados, el vehículo debe permanecer esperando hasta que uno quede libre. Para establecer el orden de atención se considera el principio de que el primero en llegar será también el primero en ser atendido.

Atención y descarga: Cuando un camión comienza a ser atendido, se determina cuánto tiempo será necesario para completar la descarga. Este tiempo puede variar dependiendo de las condiciones consideradas en el modelo. Una vez que inicia esta actividad, el sistema registra el momento en que comenzó y calcula el instante aproximado en el que terminará el proceso.

Finalización de la atención: Cuando termina la descarga, el camión sale del sistema y el espacio que estaba utilizando queda disponible nuevamente. Si existen otros vehículos esperando, el siguiente camión puede ocupar este lugar y comenzar con su atención. Al mismo tiempo, el modelo va guardando información sobre los tiempos de espera y el tiempo que cada vehículo permaneció en el centro de distribución.

Mediante este procedimiento se puede observar cómo cambia el sistema cuando aumenta o disminuye la cantidad de camiones que llegan. También permite identificar los momentos en que los espacios de atención se encuentran ocupados por mucho tiempo y cuando las esperas empiezan a aumentar. De esta manera, el modelo ofrece una representación más cercana de lo que puede ocurrir en la realidad, algo que no siempre se logra cuando solo se utilizan cálculos basados en promedios o valores fijos.

\section{Implementación y Resultados de la Simulación}
Con el modelo conceptual verificado y validado se ejecuta la simulación de eventos discretos para el escenario base (situación actual) y las dos propuestas de inversión. El experimento simula un horizonte operativo equivalente a un año de funcionamiento continuo, estructurado en múltiples réplicas independientes para garantizar significancia estadística.

Los resultados operativos iniciales del sistema bajo las condiciones actuales revelan una saturación crítica en los andenes durante las horas pico. La Tabla 9 detalla los principales indicadores de desempeño (KPIs) obtenidos tras la ejecución del modelo discreto para cada alternativa evaluada.

\begin{table}[H]
\centering
\caption{Indicadores de desempeño operativo por alternativa de inversión}
\begin{tabular}{p{5cm} c c c}
\toprule
\textbf{Indicador de Desempeño (KPI)} & \textbf{Escenario Base} & \textbf{Alternativa A} & \textbf{Alternativa B} \\
\midrule
Tiempo promedio en cola (minutos) & 84.5 & 12.3 & 28.7 \\
Longitud máxima de la cola (camiones) & 14 & 3 & 6 \\
Utilización de los andenes (\%) & 94.2\% & 71.5\% & 83.0\% \\
Tiempo total en el sistema (Cycle Time) & 125.0 min & 53.3 min & 69.7 min \\
Throughput (camiones atendidos/día) & 42 & 65 & 58 \\
\bottomrule
\end{tabular}
\begin{flushleft}
\footnotesize
\textit{Nota.} Datos obtenidos de la ejecución estocástica del modelo de eventos discretos (N=50 réplicas). Elaboración propia.
\end{flushleft}
\end{table}

Los datos demuestran que la Alternativa A reduce drásticamente el tiempo de espera y maximiza el flujo de atención, mientras que la Alternativa B ofrece una mejora moderada pero con menor despliegue de recursos físicos.

\section{Aplicación de Monte Carlo y generación de escenarios}
Si bien el modelo de eventos discretos aportó los indicadores operativos (tiempos y utilización), la decisión gerencial final requiere evaluar la rentabilidad financiera y la exposición al riesgo económico de cada alternativa, se integra el método de Monte Carlo utilizando un modelo de flujo de caja descontado a cinco años, incorporando la incertidumbre sobre la inversión inicial, los costos operativos variables y los ingresos proyectados así las variables críticas del modelo financiero se limitan con distribuciones de probabilidad asimétricas y triangulares para reflejar la variación. Mediante la ejecución de 10,000 iteraciones, el software generó el escenario completo de posibles resultados para el Valor Actual Neto (VAN) asociado a cada estrategia de inversión.

La simulación en Monte Carlo en este caso desarrollado logró definir las estimaciones financieras estáticas en perfiles de situaciones probabilísticos, evidenciando que el escenario más favorable no depende exclusivamente de los costos iniciales, sino de la capacidad de la infraestructura para absorber fluctuaciones imprevistas en la demanda externa.

\section{Análisis de Resultados y Comparación de Alternativas}
La consolidación conjunta de los resultados proporciona una perspectiva sistémica para la toma de decisiones. La evaluación comparativa ya no se reduce a comparar un único VAN estimado, sino a contrastar las distribuciones de probabilidad de éxito y los casos de exposición al riesgo de cada alternativa.

La Tabla 10 sintetiza las métricas probabilísticas de salida generadas por el modelo integrado, vinculando el desempeño financiero.

\begin{table}[H]
\centering
\caption{Evaluación probabilística integral de las alternativas de inversión}
\begin{tabular}{p{5cm} c c c}
\toprule
\textbf{Métrica de Evaluación} & \textbf{Escenario Base} & \textbf{Alternativa A} & \textbf{Alternativa B} \\
\midrule
Inversión Inicial Estimada (USD) & \$0 & \$450,000 & \$180,000 \\
Valor Esperado del VAN (USD) & \$120,000 & \$385,000 & \$410,000 \\
Probabilidad de Pérdida (VAN < 0) & 35.8\% & 8.2\% & 12.5\% \\
Percentil 5 del VAN (Peor escenario, 95\%) & -\$150,000 & \$45,000 & \$20,000 \\
Indicador Operativo Crítico & Saturación alta & Óptimo & Aceptable \\
\bottomrule
\end{tabular}
\begin{flushleft}
\footnotesize
\textit{Nota.} Elaboración propia.
\end{flushleft}
\end{table}

\section{Selección de la Alternativa para la Toma de Decisiones}
Después de revisar los resultados obtenidos en las simulaciones y comparar las diferentes situaciones que fueron analizadas, se debe tomar una decisión sobre cuál de las alternativas resulta más conveniente, no solo se considera el posible beneficio económico, sino también los problemas que podrían presentarse durante el funcionamiento del sistema.

La situación actual es descartada porque presenta un nivel de riesgo demasiado alto. Los resultados muestran que existe un 35.8\% de probabilidad de que el proyecto termine generando pérdidas y que las esperas aumenten hasta un punto donde el sistema ya no pueda responder de manera adecuada, mantener las condiciones actuales no representa una opción recomendable.

La decisión entre las dos propuestas planteadas depende principalmente de la importancia que se le dé al nivel de riesgo que se está dispuesto a asumir. La Alternativa B presenta una ventaja inicial, ya que necesita una inversión menor y puede generar mejores resultados económicos en el corto plazo, su capacidad para responder ante un aumento inesperado de la demanda es más limitada,si la cantidad de vehículos aumenta por encima de lo esperado, podrían volver a aparecer problemas de espera y acumulación,en cambio, la Alternativa A requiere una inversión mayor debido a la ampliación de las instalaciones y la incorporación de nuevos trabajadores. A pesar de este costo inicial, los resultados muestran que ofrece mejores condiciones para atender un mayor número de vehículos. Con esta opción, el tiempo promedio de espera se reduce hasta 12.3 minutos y se alcanza una capacidad de atención de aproximadamente 65 camiones por día. Además, la probabilidad de obtener pérdidas económicas disminuye hasta un 8.2\%.

Se decide elegir la Alternativa A: Ampliación de Capacidad Física. Que representa un mayor gasto al inicio, los resultados indican que permite trabajar con un menor nivel de riesgo y responder mejor ante posibles aumentos de la demanda. Por lo tanto, esta alternativa ofrece mejores condiciones para mantener el funcionamiento del sistema y favorecer el crecimiento del proyecto en los próximos años.

% ==============================================================================
% CONCLUSIONES
% ==============================================================================
\chapter*{Conclusiones}
\addcontentsline{toc}{chapter}{Conclusiones}

El desarrollo de esta monografía permite comprender que la simulación es una herramienta que puede ayudar a analizar situaciones que presentan cambios e incertidumbre. A diferencia de los modelos que trabajan solo con valores promedio o condiciones fijas, la simulación permite representar diferentes escenarios sin tener que modificar directamente un proceso real. Esto resulta útil porque permite conocer de manera anticipada algunos problemas que podrían presentarse y evaluar diferentes opciones antes de tomar una decisión.

La simulación de eventos discretos permite observar con mayor detalle cómo se desarrolla un proceso a medida que pasa el tiempo. A través de este método se puede representar la llegada de personas, vehículos u otros elementos, así como los tiempos de espera y el uso de los recursos disponibles. Su aplicación permite reconocer situaciones donde la capacidad no es suficiente, identificar acumulaciones y conocer qué partes del proceso necesitan una mejora. Por ello, resulta una herramienta adecuada para estudiar problemas relacionados con la atención, los tiempos de espera y la distribución de los recursos.

El método de Monte Carlo permite trabajar con situaciones donde los valores pueden cambiar y no se conocen con exactitud. Al generar una gran cantidad de posibles escenarios, se puede observar cómo podrían variar los resultados de un proyecto dependiendo de factores como los costos, los ingresos o la demanda. Esto permite tener una idea más amplia sobre los posibles resultados y conocer la posibilidad de obtener ganancias o pérdidas, en lugar de basarse solamente en un único valor esperado.

El uso conjunto de la simulación de eventos discretos y Monte Carlo permite ampliar el análisis. Mientras un método ayuda a conocer cómo puede funcionar un proceso ante diferentes condiciones, el otro permite estudiar cómo los cambios en determinadas variables pueden modificar los resultados. Esta combinación hace posible evaluar tanto los posibles cambios externos como la capacidad real de un proceso para responder ante ellos. De esta forma, las decisiones pueden apoyarse en una mayor cantidad de información y no depender solamente de estimaciones o promedios.

También se puede concluir que la elección de las herramientas utilizadas para realizar una simulación debe adaptarse a las características de cada problema. Python y SimPy representan alternativas flexibles para desarrollar modelos mediante programación, mientras que herramientas como Crystal Ball pueden facilitar el análisis cuando se trabaja con hojas de cálculo. La elección dependerá de factores como la dificultad del modelo, los conocimientos de las personas encargadas del análisis y los recursos disponibles. Por ello, no existe una única herramienta que sea adecuada para todos los casos, sino que su elección debe responder a las necesidades particulares de cada situación.
% ==============================================================================
% REFERENCIAS BIBLIOGRÁFICAS
% ==============================================================================
\renewcommand{\bibname}{Referencias Bibliográficas} % Cambia el título por defecto
\cleardoublepage
\addcontentsline{toc}{chapter}{Referencias Bibliográficas}

% Llama al estilo y al archivo .bib
% ==============================================================================
% REFERENCIAS BIBLIOGRÁFICAS
% ==============================================================================
\chapter*{Referencias Bibliográficas}
\addcontentsline{toc}{chapter}{Referencias Bibliográficas}

\begin{list}{}{
    \setlength{\leftmargin}{1.25cm}
    \setlength{\itemindent}{-1.25cm}
    \setlength{\parsep}{0pt}
    \setlength{\itemsep}{12pt}
}

\item Albright, S. C., \& Winston, W. L. (2015). \textit{Business Analytics: Data Analysis \& Decision Making} (5ta ed.). Cengage Learning.

\item Banks, J., Carson, J. S., Nelson, B. L., \& Nicol, D. M. (2014). \textit{Discrete-Event System Simulation} (5ta ed.). Pearson.

\item Dagkakis, G., \& Heavey, C. (2016). A review of open source discrete event simulation software for operations research. \textit{Journal of Simulation, 10}(3), 193--206.

\item Greasley, A. (2003). \textit{Simulation Modelling for Business}. Ashgate Publishing.

\item Jahangirian, M., Eldabi, T., Naseer, A., Stergioulas, L. K., \& Young, T. (2010). Simulation in manufacturing and business: A review. \textit{European Journal of Operational Research, 203}(1), 1--13.

\item Kelton, W. D., Sadowski, R. P., \& Zupick, N. B. (2015). \textit{Simulation with Arena} (6ta ed.). McGraw-Hill Education.

\item Kwak, Y. H., \& Ingall, L. (2007). Exploring Monte Carlo simulation applications for project management. \textit{Risk Management, 9}(1), 44--57.

\item Law, A. M. (2015). \textit{Simulation Modeling and Analysis} (5ta ed.). McGraw-Hill Education.

\item Mun, J. (2006). \textit{Modeling Risk: Applying Monte Carlo Risk Simulation, Strategic Real Options, Stochastic Forecasting, and Portfolio Optimization} (2da ed.). John Wiley \& Sons.

\item Pidd, M. (2004). \textit{Computer Simulation in Management Science} (5ta ed.). John Wiley \& Sons.

\item Raychaudhuri, S. (2008). Introduction to Monte Carlo simulation. \textit{2008 Winter Simulation Conference}, 91--100.

\item Robinson, S. (2012). Tutorial: Simulation conceptual modeling. \textit{2012 Winter Simulation Conference}, 1--15.

\item Robinson, S. (2014). \textit{Simulation: The Practice of Model Development and Use} (2da ed.). Palgrave Macmillan.

\item Rubinstein, R. Y., \& Kroese, D. P. (2016). \textit{Simulation and the Monte Carlo Method} (3ra ed.). John Wiley \& Sons.

\item Sargent, R. G. (2013). Verification and validation of simulation models. \textit{Journal of Simulation, 7}(1), 12--24.

\item Vose, D. (2008). \textit{Risk Analysis: A Quantitative Guide} (3ra ed.). John Wiley \& Sons.

\end{list}
\end{document}

### Ejes de Investigación

* Planteamiento de variables y restricciones del modelo.
* Desarrollo y resolución analítica.
* Interpretación de resultados enfocados en la toma de decisiones para la administración.

---
<div align="center">
  <p>Desarrollado por <b>Anghelo Támara Ramírez</b></p>
</div>
