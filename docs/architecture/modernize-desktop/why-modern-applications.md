---
title: Aplicaciones de escritorio modernas, ¿por qué?
description: Obtenga información sobre las tecnologías de escritorio como Windows Forms, WPF y UWP en el mundo moderno.
ms.date: 12/29/2020
ms.openlocfilehash: 8489e41c973bb472a23bca38e9374c36e4cdd366
ms.sourcegitcommit: 632818f4b527e5bf3c48fc04e0c7f3b4bdb8a248
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/20/2021
ms.locfileid: "98615898"
---
# <a name="why-modern-desktop-applications"></a>Aplicaciones de escritorio modernas, ¿por qué?

## <a name="introduction"></a>Introducción

### <a name="a-story-of-one-company"></a>Un caso de una compañía

De vuelta a la primera 2000s, una empresa multinacional comenzó a desarrollar una solución de escritorio distribuida para intercambiar información entre distintas ramas de la empresa y ejecutar operaciones optimizadas en unidades centralizadas. Han elegido un marco de trabajo nuevo denominado Windows Forms (también conocido como WinForms) para su desarrollo de aplicaciones. A lo largo de los años, el proyecto evolucionó en una aplicación madura, bien probada y probada en el tiempo con cientos de miles de líneas de código. El tiempo pasado y .NET Framework 2,0 ya no es la nueva tecnología de acceso frecuente. Los desarrolladores que trabajan en esta aplicación están enfrentando un dilema. Les gustaría usar la pila de tecnologías más reciente en su desarrollo y hacer que su aplicación tenga el aspecto y "sentir" moderno. Al mismo tiempo, no quieren salir del excelente producto que han creado en 15 años y volver a escribir toda la aplicación desde cero.

### <a name="your-story"></a>Su historia

Es posible que se encuentre en el mismo barco, donde tiene aplicaciones de Windows Forms o Windows Presentation Foundation (WPF) que han demostrado su confiabilidad a lo largo de los años. Probablemente quiera seguir usando estas aplicaciones durante muchos más años. Al mismo tiempo, dado que esas aplicaciones se escribieron hace algún tiempo, podrían faltar funcionalidades como la apariencia moderna, el rendimiento, la integración con nuevos dispositivos y características de la plataforma, etc., lo que les da la sensación de "antigua tecnología". Hay otro problema que podría interesarle como desarrollador. Mientras trabaja en las versiones más antiguas de .NET Framework y el mantenimiento de las aplicaciones que se escribieron hace, es posible que no esté aprendiendo nuevas tecnologías y que falten en la creación de conocimientos técnicos modernos. Si es su caso, este libro es para usted.

## <a name="desktop-applications-nowadays"></a>Aplicaciones de escritorio en la actualidad

Antes del lanzamiento de Internet, las aplicaciones de escritorio eran el método principal para crear sistemas de software. Los desarrolladores pueden elegir cualquier lenguaje de programación, como COBOL, Fortran, VB6 o C++. Pero cuando desarrollaron herramientas pequeñas o arquitecturas distribuidas complejas, eran todas las aplicaciones de escritorio.

Después, las tecnologías de Internet empezaron a desaprovechar el mundo de desarrollo y ganar más ingenieros con ventajas como la implementación sencilla y los procesos de distribución simplificados. El hecho de que una vez que se implementó una aplicación web en producción, todos los usuarios obtuvieron actualizaciones automáticas hicieron un gran impacto en la agilidad del software.

Sin embargo, la infraestructura de Internet, los protocolos subyacentes y los estándares como HTTP y HTML no se diseñaron para compilar aplicaciones complejas. De hecho, el importante esfuerzo de desarrollo después era tener un solo objetivo: ofrecer a las aplicaciones web las mismas capacidades que tienen las aplicaciones de escritorio, como la entrada rápida de datos y la administración de Estados.

Aunque las aplicaciones web y móviles han crecido a un ritmo increíble, para determinadas tareas, las aplicaciones de escritorio aún mantienen el número en términos de eficiencia y rendimiento. Esto explica por qué hay millones de desarrolladores que compilan sus proyectos con WPF y WinForms y que la cantidad de esas aplicaciones crece constantemente.

Estas son algunas de las razones para elegir aplicaciones de escritorio en su desarrollo:

- Las aplicaciones de escritorio tienen una mejor interacción con el equipo del usuario.
- El rendimiento de las aplicaciones de escritorio para cálculos complejos es mucho mayor que el rendimiento de las aplicaciones Web.
- La ejecución de la lógica personalizada en el lado cliente es posible pero mucho más difícil con una aplicación Web.
- El uso de multithreading es más fácil y eficaz en una aplicación de escritorio.
- La curva de aprendizaje para diseñar interfaces de usuario (IUS) no es pronunciada. Y para WinForms, es intuitivo con la experiencia de arrastrar y colocar del diseñador de Windows Forms.
- Es fácil empezar a codificar y probar los algoritmos sin necesidad de configurar una infraestructura de servidor ni de preocuparse por los problemas de conectividad, los firewalls y la compatibilidad del explorador.
- La depuración es eficaz en comparación con la depuración web.
- El acceso a los dispositivos de hardware, como la cámara, el Bluetooth o los lectores de tarjeta, es fácil.
- Dado que la tecnología ha estado en todo momento, hay muchos expertos y una base de conocimiento disponible para desarrollar aplicaciones de escritorio.

Por lo tanto, como puede ver, el desarrollo para escritorio es excelente por muchas razones. La tecnología es madura y se prueba el tiempo, el ciclo de desarrollo es rápido, la depuración es eficaz y posiblemente, las aplicaciones de escritorio tienen menos complejidad y es más fácil empezar a trabajar con.

Microsoft ofreció muchas tecnologías de escritorio de la interfaz de usuario a lo largo de los años de la versión de Win32 incluida en 1995 a Plataforma universal de Windows (UWP) publicada en 2016.

![Tecnologías de escritorio de Microsoft](./media/why-modern-applications/microsoft-desktop-technologies.png)

Según una encuesta publicada por Telerik el 2016 de abril, las tecnologías más populares para compilar aplicaciones de escritorio de Windows son Windows Forms, WPF y UWP.

![La encuesta de Telerik muestra Windows Forms, WPF y UWP como las tecnologías de escritorio más populares](./media/why-modern-applications/telerik-survey.png)

Puede desarrollar en cualquiera de ellas mediante C# y Visual Basic, pero echemos un vistazo más de cerca.

### <a name="windows-forms"></a>Windows Forms

Se lanzó por primera vez en 2002, Windows Forms es un marco administrado y es la tecnología de escritorio más antigua y más usada que se basa en el motor de la interfaz de dispositivo gráfico (GDI) de Windows. Ofrece una experiencia fluida de arrastrar y colocar para desarrollar interfaces de usuario en Visual Studio.  Al mismo tiempo, Windows Forms se basa en el diseñador de Visual Studio como la forma principal de desarrollar la interfaz de usuario, por lo que no es trivial crear componentes visuales a partir del código.

En la lista siguiente se resumen las principales características de Windows Forms:

- Tecnología madura con gran cantidad de ejemplos de código y documentación.
- Diseñador eficaz y productivo. No es tan práctico diseñar la interfaz de usuario "desde el código".
- Fácil e intuitivo de aprender, gracias a la experiencia de arrastrar y colocar del diseñador.
- Compatible con cualquier versión de Windows.
- Compatible con .NET Core 3,0 y versiones posteriores.

### <a name="wpf"></a>WPF

En función de la especificación del lenguaje XAML, WPF favorece una separación clara entre la interfaz de usuario y el código. XAML ofrece funcionalidades como la creación de plantillas, el estilo y el enlace, que es adecuado para compilar aplicaciones de gran tamaño. Como Windows Forms, es un marco de trabajo administrado, pero el diseño es modular y reutilizable.

Estas son las principales características de WPF:

- Tecnología consolidada.
- El diseñador está disponible, pero normalmente los desarrolladores prefieren crear el diseño a partir del código mediante XAML declarativo.
- La curva de aprendizaje es más pronunciada que Windows Forms.
- Compatible con cualquier versión de Windows.
- Compatible con .NET Core 3,0 y versiones posteriores.

### <a name="uwp"></a>UWP

UWP no es solo un marco de presentación como WPF y Windows Forms, sino que también es una plataforma. Esta plataforma tiene:

- Su propio conjunto de API (la API de Windows Runtime).
- Un nuevo sistema de implementación (MSIX)
- Un modelo de ciclo de vida de la aplicación moderno (para el consumo de batería baja).
- Un nuevo sistema de administración de recursos (basado en archivos PRI).

La plataforma se creó para admitir todo tipo de sistemas de entrada (como la tinta, la entrada táctil, el controlador de juegos, el mouse, el teclado, la mirada, etc.) en todos los factores de forma con el rendimiento y el consumo bajo de la batería en mente. Por estos motivos, el Shell del sistema operativo Windows 10 usa partes de la plataforma UWP.

![Estructura de UWP](./media/why-modern-applications/uwp-structure.png)

UWP contiene un marco de presentación basado en XAML, como WPF, pero tiene algunas diferencias importantes, como:

- Las aplicaciones se ejecutan en contenedores de aplicaciones. Los contenedores de aplicaciones controlan los recursos a los que puede acceder una aplicación para UWP.
- Solo se admite en Windows 10.
- Las aplicaciones se pueden implementar a través de Microsoft Store para facilitar la implementación.
- Diseñado como parte de la API de Windows Runtime.
- Contiene un amplio conjunto de controles integrados muy completos y controles adicionales disponibles a través de los paquetes NuGet de la biblioteca de interfaz de usuario de Microsoft (biblioteca WinUI) actualizados cada pocos meses.

## <a name="a-tale-of-two-platforms"></a>Un testigo de dos plataformas

En los últimos 20 años, mientras que las tecnologías de escritorio de la interfaz de usuario estaban creciendo y después de la ruta de acceso de Windows Forms a UWP, el hardware también ha evolucionado desde unidades de PC de gran peso con pequeños monitores de CRT a monitores de alta PPP y tabletas ligeras y teléfonos con distintas técnicas de entrada de datos, como la entrada táctil y la entrada manuscrita. Estos cambios han dado lugar a la creación de dos conceptos diferentes: una aplicación de escritorio y una aplicación moderna. Una aplicación moderna es aquella que considera diferentes factores de forma de dispositivo, varios métodos de entrada y salida, y aprovecha las características de escritorio modernas mientras se ejecuta en un modelo de ejecución en espacio aislado. La aplicación de escritorio (tradicional), por otro lado, es una aplicación que necesita una interfaz de usuario sólida con una alta densidad de controles que funciona mejor con un mouse y un teclado.

En la tabla siguiente se describen las diferencias entre los dos conceptos:

|   | Aplicación moderna | Aplicación de escritorio |
| --- | --- | --- |
| Seguridad | Contenía &amp; elementos fundamentales excelentes. Diseñado desde cero para respetar la privacidad del usuario, administrar la duración de la batería y centrarse en proteger el dispositivo.  | &amp;Nivel de seguridad de administración de usuarios. Tiene acceso nativo al registro y a las carpetas de la unidad de disco duro. |
| Implementación | La plataforma administra la instalación y las actualizaciones.   | MSI, actualizaciones de instaladores personalizados &amp; . Tradicionalmente, una fuente de problemas para desarrolladores y administradores de ti.  |
| Distribución | Paquetes firmados de distribución de confianza &amp; . La distribución se realiza desde una fuente de confianza y nunca desde la Web.  | Web, &amp; distribución personalizada de SCCM. Ningún control sobre lo que se instala, afecta a todo el equipo.   |
| UI | Interfaz de usuario moderna. Diferentes mecanismos de entrada, entrada manuscrita, táctil, controlador para juegos, teclado, Mouse, etc.  | Windows Forms, WPF, MFC. Diseñado para el mouse y el teclado para una interfaz de usuario densa y para obtener la máxima productividad del escritorio.  |
| data | Primeros datos en la nube con información detallada. Origen de veracidad en la nube. Información para saber lo que ocurre con la aplicación y cómo funciona.  | Datos locales. Las aplicaciones de escritorio tradicionales normalmente necesitan algunos datos locales.  |
| Diseño | Diseñado para reutilizarlo. Reutilización en mente entre distintas plataformas, front-end y back-end, que ejecutan recursos en muchos lugares como sea posible.  | Diseñado solo para escritorio de Windows  |

Como parte del compromiso de proporcionar a los desarrolladores las mejores herramientas para compilar aplicaciones, Microsoft ofrece un gran esfuerzo para aportar estos conceptos, o incluso podemos decir plataformas, más cerca de ofrecer a los desarrolladores lo mejor de ambos mundos. Para ello, Microsoft ha realizado un esfuerzo bidireccional entre las dos plataformas.

![Esfuerzo bidireccional entre aplicaciones de escritorio y aplicaciones modernas](./media/why-modern-applications/bidirectional-effort.png)

1. Mueva escenarios de aplicaciones de escritorio a la plataforma de aplicaciones moderna. El desarrollo de escritorio tradicional sigue siendo popular porque aborda ciertos escenarios bien. Tiene sentido tomar estos escenarios comunes de escritorio y incorporarlos a la plataforma de escritorio moderna para que la plataforma sea totalmente compatible.

    ![Traslado de escenarios de aplicaciones de escritorio a la plataforma de aplicaciones modernas](./media/why-modern-applications/desktop-to-modern.png)

1. Trasladar las características modernas de la aplicación a las aplicaciones de escritorio. En el caso de las aplicaciones de escritorio existentes que necesitan una forma de aprovechar las capacidades modernas sin necesidad de volver a escribir desde cero, las características de la plataforma de aplicaciones modernas se insertan en la aplicación de escritorio.

    ![Traslado de características de aplicaciones modernas a aplicaciones de escritorio](./media/why-modern-applications/modern-to-desktop.png)

En este libro, nos centraremos en la segunda parte y mostraremos cómo puede modernizar las aplicaciones de escritorio existentes.

## <a name="paths-to-modernization"></a>Rutas de acceso a modernización

La estructura de esta guía refleja tres ejes distintos para llevar a cabo la modernización: características modernas, implementación e instalación.

### <a name="modern-features"></a>Características modernas

Supongamos que tiene una aplicación Windows Forms en funcionamiento que un representante de ventas de su empresa usa para rellenar el pedido de un cliente. Se incluye un nuevo requisito para permitir que el cliente firme el pedido con un lápiz de Tablet PC. La entrada manuscrita es nativa en los sistemas operativos y tecnologías actuales, pero no estaba disponible cuando se desarrolló la aplicación.

Esta ruta de acceso le mostrará cómo puede aprovechar las características modernas del escritorio en el desarrollo de escritorio existente.

### <a name="deployment"></a>Implementación

Los ciclos de desarrollo modernos se han destacado para proporcionar agilidad sobre cómo se implementan las nuevas versiones de las aplicaciones en cada usuario único. Dado que las aplicaciones de Windows Forms y WPF se basan en una versión determinada del .NET Framework que deben estar presentes en el equipo, no pueden aprovechar las nuevas características de la versión .NET Framework sin la intervención de los usuarios de TI con el riesgo de tener efectos secundarios para otras aplicaciones que se ejecutan en el mismo equipo. Ha limitado el ritmo de innovación para que los desarrolladores les obliguen a permanecer en versiones obsoletas del .NET Framework.

Desde el lanzamiento de .NET Core 3,0, puede aprovechar un nuevo enfoque de la implementación de varias versiones de .NET en paralelo y la especificación de la versión de .NET a la que debe dirigirse cada aplicación. De este modo, puede usar las características más recientes en una aplicación mientras está seguro de que no va a interrumpir otras aplicaciones.

### <a name="installation"></a>Instalación

Las aplicaciones de escritorio siempre dependen de algún tipo de proceso de instalación antes de que el usuario pueda empezar a usarlas. Este hecho ha incorporado el juego a un conjunto de tecnologías, desde MSI y ClickOnce hasta instaladores personalizados o incluso implementación de XCOPY. Cualquiera de estos métodos se ocupa de los problemas delicados porque las aplicaciones necesitan una manera de tener acceso a los recursos compartidos de la máquina. A veces, la instalación necesita tener acceso al registro para insertar o actualizar nuevos valores de clave, a veces para actualizar los archivos dll compartidos a los que hace referencia la aplicación principal. Este comportamiento provoca un dolor continuo para los usuarios y crea esta percepción que, una vez que se instala alguna aplicación, el equipo nunca será el mismo, incluso aunque se desinstale después.

En este libro, introduciremos una nueva forma de instalar aplicaciones con MSIX que resuelve el problema descrito anteriormente. Aprenderá cómo puede configurar fácilmente el empaquetado, la instalación y las actualizaciones de la aplicación.

>[!div class="step-by-step"]
>[Anterior](index.md)
>[Siguiente](whats-new-dotnet.md)
