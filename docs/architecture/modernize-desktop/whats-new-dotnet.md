---
title: ¿Qué novedades hay en .NET para escritorio?
description: Obtenga información sobre .NET, las diferencias entre .NET y .NET Framework y las nuevas características que se agregaron.
ms.date: 12/29/2020
ms.openlocfilehash: 03dea849ad8a797b917dca953d93be6878d7ec72
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102106186"
---
# <a name="whats-new-with-net-for-desktop"></a>¿Qué novedades hay en .NET para escritorio?

A partir de .NET Core 3,0, .NET admite Windows Forms y WPF. Por lo tanto, ahora tiene la opción de elegir entre .NET Framework y .NET para las aplicaciones de escritorio. En este capítulo se describe lo que es .NET y cuáles son las ventajas de las aplicaciones de escritorio.

## <a name="the-motivation-behind-net-core"></a>La motivación detrás de .NET Core

Desde su lanzamiento en 2002, .NET Framework ha evolucionado a lo largo de los años para admitir muchas tecnologías, como Windows Forms, ASP.NET, Entity Framework, tienda Windows y muchas otras. Todos ellos son de naturaleza diferente. Por lo tanto, Microsoft se estaba aproximando a esta evolución tomando partes de la .NET Framework y creando una pila de aplicaciones diferente para cada tecnología. De este modo, se pueden personalizar las capacidades de desarrollo para las necesidades de la pila específica, lo que maximiza el potencial de todas las plataformas. Esto conduce a la fragmentación de las versiones de los .NET Framework que se mantienen en distintos equipos independientes. Todas estas pilas tienen una estructura común que contiene un modelo de aplicación, un marco de trabajo y un tiempo de ejecución, pero difieren en la implementación de cada una de estas partes.

Si el destino es solo una de estas plataformas, puede utilizar este modelo. Sin embargo, en muchos casos es posible que necesite más de una plataforma de destino en la misma solución. Por ejemplo, la aplicación puede tener una parte del administrador del escritorio, un sitio web orientado al cliente que comparte la lógica de back-end que se ejecuta en un servidor e incluso un cliente móvil. En este caso, se necesita una experiencia de codificación unificada que puede abarcar todas las verticales de .NET.

En el momento en que se lanzó Windows 8, nació el concepto de bibliotecas de clases portables (PCL). Originalmente, el .NET Framework se diseñó en torno a la suposición de que siempre se implementaría como una sola unidad, por lo que la [factorización](https://wikipedia.org/wiki/Decomposition_(computer_science)) no supone un problema. Para solucionar el problema del uso compartido de código entre verticales, la fuerza de conducción era la forma de refactorizar el marco de trabajo. La idea de los contratos es proporcionar un área expuesta de API bien factorizada. Los contratos son simplemente ensamblados que se compilan con y que se han diseñado teniendo en cuenta las dependencias entre ellos.

Esto conduce a la razón de las diferencias de API entre los verticales en el nivel de ensamblado, en lugar del nivel de API individual que teníamos antes. Este aspecto ha habilitado una experiencia de biblioteca de clases que puede tener como destino varios tipos verticales, también conocidos como bibliotecas de clases portables.

![Historial de versiones de .NET Framework](./media/whats-new-dotnet-core/release-history.png)

Con PCL, la experiencia de desarrollo se unifica en vertical en función de la forma de la API. También se aborda la necesidad de crear bibliotecas que se ejecutan en diferentes verticalmente. Pero hay un gran desafío: las API solo son portátiles cuando la implementación se mueve hacia delante en todas las verticales.

Un enfoque mejor es unificar las implementaciones entre verticales proporcionando una implementación bien factorizada en lugar de una vista bien factorizada. Es mucho más sencillo pedir a cada equipo que posea un componente específico que piense en cómo funcionan sus API en todos los verticales que al intentar proporcionar una pila de API coherente en primer lugar. Aquí es donde entra .NET Standard. Vea los detalles en la sección siguiente.

Otro gran desafío tiene que hacer con cómo se implementa el .NET Framework. El .NET Framework es un marco de trabajo para todo el equipo. Cualquier cambio que se realice en él afectará a todas las aplicaciones que tengan una dependencia. Aunque este modelo de implementación tiene muchas ventajas, como reducir el espacio en disco y el acceso centralizado a los servicios, presenta algunos problemas.

Para empezar, es difícil que los desarrolladores de aplicaciones tomen una dependencia en un marco de trabajo lanzado recientemente. Tienen que tomar una dependencia del sistema operativo más reciente o proporcionar un instalador de la aplicación que instale el .NET Framework junto con la aplicación. Si es un desarrollador web, es posible que ni siquiera tenga esta opción, ya que el Departamento de ti establece la versión compatible con el servidor.

Incluso si está dispuesto a desplazarse por el problema de proporcionar un instalador para encadenar en el .NET Framework el programa de instalación, puede que la actualización del .NET Framework pueda interrumpir otras aplicaciones.

A pesar de los esfuerzos de proporcionar versiones anteriores compatibles del marco, hay cambios compatibles que pueden interrumpir las aplicaciones. Por ejemplo, al agregar una interfaz a un tipo existente se puede cambiar el modo en que este tipo se serializa y provocar problemas de interrupción en función del código existente. Dado que la base instalada de .NET Framework es enorme, la lucha contra estos escenarios de última hora reduce el ritmo de las innovaciones en el .NET Framework.

Para solucionar todos estos problemas, Microsoft ha desarrollado .NET Core para abordar la evolución de la plataforma .NET.

## <a name="introduction-to-net-core"></a>Introducción a .NET Core

.NET Core es la evolución de la tecnología de .NET de Microsoft en una plataforma modular, multiplataforma, de código abierto y preparada para la nube. Se ejecuta en Windows, macOS y Linux con planes para ejecutarse también en arquitecturas basadas en ARM como Android y IoT.

El propósito de .NET Core es proporcionar una plataforma unificada para todos los tipos de aplicaciones, entre las que se incluyen las aplicaciones móviles, multiplataforma y Windows. [.Net Standard](../../standard/net-standard.md) permite esto proporcionando API base compartidas, que cada modelo de aplicación necesita y excluye cualquier API específica del modelo de aplicación.

Este marco de trabajo proporciona a las aplicaciones muchas ventajas en cuanto a eficacia y rendimiento, lo que simplifica el empaquetado y la implementación en las diferentes plataformas admitidas.

Las ventajas de .NET Core proceden de estas tres características:

- **Multiplataforma:** Permite la ejecución de aplicaciones en distintas plataformas (Windows, macOS y Linux).
- **Código abierto:** la plataforma .net Core es de código abierto y está disponible a través de Github, con lo que se fomenta la transparencia y las contribuciones de la comunidad.
- **Compatible:** Microsoft es compatible oficialmente con .NET Core.

A partir de .NET Core 3,0, además de la compatibilidad existente con la web y la nube, también se admiten dominios de escritorio, IoT y AI. El objetivo de este marco de trabajo es impresionante: para dirigirse a todos los tipos de desarrollo de .NET presentes y futuros. Microsoft planea completar esta visión con .NET 5 al final de 2020. El nombre "principal" se ha quitado para reforzar su unicidad en el mundo de .NET.

## <a name="net-5-is-net-core-vnext"></a>.NET 5 es .NET Core vNext

.NET 5 es el siguiente paso adelante con .NET Core. .NET 5,0 pretende mejorar .NET de varias maneras clave:

- Producir un único runtime y un marco de .NET que se pueda usar en todas partes y que tenga comportamientos de runtime y experiencias de desarrollador uniformes.
- Ampliar las funcionalidades de .NET con las mejores características de .NET Core, .NET Framework, Xamarin y Mono.
- Desarrollar el producto a partir de un solo código base que mejore todos los escenarios, que los desarrolladores (Microsoft y la comunidad) puedan expandir y en el que puedan trabajar juntos.

Esta nueva versión y dirección son un cambio de juego para .NET. Con .NET 5, los archivos de proyecto y código tendrán la misma apariencia, independientemente del tipo de aplicación que se esté compilando. Tendrá acceso a las mismas funcionalidades de tiempo de ejecución, API y lenguaje con cada aplicación. Esto incluye nuevas [mejoras de rendimiento](https://devblogs.microsoft.com/dotnet/performance-improvements-in-net-5/) que se confirman en tiempo de ejecución, prácticamente a diario. Para obtener más información, consulte las novedades [de .net 5](../../core/dotnet-five.md).

![Todos los dominios de .NET 5](./media/whats-new-dotnet-core/all-domains-of-dotnet5.png)

## <a name="net-framework-vs-net-5"></a>.NET Framework frente a .NET 5

Ahora que comprende la relevancia de .NET, es posible que se pregunte qué sucede con .NET Framework. Podría plantearse preguntas como: ¿tiene que abandonarla? ¿Va a desaparecer? ¿Cuáles son mis opciones para modernizar las aplicaciones que tengo en .NET Framework?

En 2019 se lanzó la última versión del **.NET Framework-4,8** . Incluye tres mejoras importantes para las aplicaciones de escritorio:

- **Explorador moderno y controles multimedia**: hoy en día, las aplicaciones de escritorio de .net usan Internet Explorer y Windows Media Player para mostrar archivos multimedia y reproducir archivos multimedia. Dado que estos controles heredados no muestran el código HTML más reciente ni reproducen los últimos archivos multimedia, se agregaron nuevos controles que aprovechan las ventajas de Microsoft Edge y los reproductores multimedia más recientes que admiten los estándares más recientes.
- **Acceso a los controles de UWP**: UWP contiene nuevos controles que aprovechan las características de Windows y las pantallas táctiles más recientes. No tiene que volver a escribir las aplicaciones para usar estas nuevas características y controles, por lo que puede usar estas nuevas características en el código existente de WPF o Windows Forms.
- **Mejoras en el nivel de PPP alto**: la resolución de las pantallas está aumentando a resoluciones de 4k y 8k. Por lo tanto, .NET Framework 4,8 agrega nuevas mejoras de HDPI para asegurarse de que las aplicaciones de Windows Forms y WPF existentes pueden tener un aspecto excelente en estas nuevas pantallas.

Como .NET Framework está instalado en millones de máquinas, Microsoft seguirá admitiendo este servicio, pero no agregará nuevas características.

.NET 5 es la versión de código abierto, multiplataforma y de movimiento rápido de la familia .NET. Debido a su naturaleza en paralelo, puede realizar cambios sin el miedo de interrumpir ninguna aplicación. Esto significa que .NET obtendrá nuevas API y características de lenguaje con el tiempo que .NET Framework no. Además, **.net** ya tiene características que eran imposibles para .NET Framework, como:

- **Versiones en paralelo de .net que admiten Windows Forms y WPF**: Esto resuelve el problema de efectos secundarios al actualizar la versión del marco de trabajo de la máquina. Se pueden instalar varias versiones de .NET en el mismo equipo y cada aplicación especifica la versión de .NET que debe usar. Incluso más, ahora puede desarrollar y ejecutar Windows Forms y WPF sobre .NET.
- **Insertar .net directamente en una aplicación**: puede implementar .net como parte del paquete de aplicación. Esto le permite aprovechar la última versión, las características y las API sin tener que esperar a que se instale una versión específica en el equipo.
- Aproveche **las ventajas de las características de .net**: .net Core es la versión de .net de código abierto de movimiento rápido. Su naturaleza en paralelo permite la rápida introducción de nuevas API innovadoras y mejoras de las bibliotecas de clases base (BCL) sin el riesgo de que se interrumpa la compatibilidad. Ahora Windows Forms y las aplicaciones de WPF pueden beneficiarse de las características de .NET más recientes, que también incluye correcciones más fundamentales para el rendimiento en tiempo de ejecución, la compatibilidad con alta calidad de PPP, etc.

Una parte esencial de la guía básica de Microsoft era facilitar a los desarrolladores la migración de aplicaciones a .NET Core y en versiones posteriores a .NET 5. Sin embargo, si ya tiene aplicaciones .NET Framework, no debe sentirse a la presión de pasar a .NET 5. .NET Framework serán totalmente compatibles y siempre formarán parte de Windows. Sin embargo, si desea usar las características de lenguaje y las API más recientes en el futuro, tendrá que trasladar sus aplicaciones a .NET.

En el caso de las nuevas aplicaciones de escritorio, se recomienda empezar directamente en .NET 5. Es ligero y multiplataforma, se ejecuta en paralelo, tiene un alto rendimiento y se adapta perfectamente a las arquitecturas de microservicios y contenedores.

![Puede actualizar las aplicaciones .NET Framework con la última versión de .NET Framework o migrar las aplicaciones a .NET Core.](./media/whats-new-dotnet-core/framework-vs-core.png)

## <a name="net-standard-vs-pcl"></a>.NET Standard frente a PCL

[.NET Standard](../../standard/net-standard.md) es una especificación formal de las API de .NET que se prevé que estén disponibles en todas las implementaciones de .NET. La finalidad de .NET Standard es establecer una mayor uniformidad en el ecosistema de .NET. .NET Standard es una especificación de las API de .NET que constituyen un conjunto uniforme de contratos para compilar el código. Estos contratos se implementan en cada tipo de .NET, lo que permite la portabilidad en diferentes implementaciones de .NET.

.NET Standard habilita los escenarios clave siguientes:

- Define un conjunto uniforme de API de bibliotecas de clases base para todas las implementaciones de .NET que se van a implementar, independientemente de la carga de trabajo.
- Permite a los desarrolladores generar bibliotecas portátiles que se pueden usar en las implementaciones de .NET con este mismo conjunto de API.

.NET Standard es la evolución de PCL y en la lista siguiente se muestran las diferencias fundamentales entre .NET Standard y PCL:

- .NET Standard es un conjunto de API de seleccionada, seleccionado por Microsoft. PCL no.
- Las API que contiene una PCL dependen de las plataformas que elija como destino al crearla. Esto hace que una PCL solo se pueda compartir para los destinos específicos que elija.
- .NET Standard es independiente de la plataforma, puede ejecutarse en cualquier lugar, en Windows, macOS, Linux, etc.
- PCL también puede ejecutarse en varias plataformas, pero tienen un alcance más limitado. PCL solo puede tener como destino un conjunto limitado de plataformas.

## <a name="new-desktop-features-in-net-core"></a>Nuevas características de escritorio en .NET Core

### <a name="support-for-windows-forms-and-wpf"></a>Compatibilidad con Windows Forms y WPF

Windows Forms y WPF forman parte de .NET Core desde la versión 3,0. Ambos marcos de presentación son solo para Windows, por lo que no son multiplataforma. Puede pensar en WPF como una capa enriquecida en DirectX y Windows Forms como una capa más delgada en GDI+. WPF y Windows Forms realizan un gran trabajo de exponer y ejercitar gran parte de la funcionalidad de aplicaciones de escritorio de Windows. Por tanto Windows Forms y WPF están disponibles para .NET Core y .NET Framework. Ahora puede iniciar las nuevas aplicaciones de escritorio que tienen como destino .NET Core y migrar las existentes desde .NET Framework a .NET Core.

Se lanzó una nueva versión de .NET Standard, versión 2,1, al mismo tiempo que .NET Core 3,0. Como se esperaba, las versiones de .NET Core 3. x admiten .NET Standard 2,1 y versiones anteriores.

Además, es importante tener en cuenta que tanto las implementaciones de Windows Forms como de WPF de .NET Core son de código abierto.

### <a name="xaml-islands"></a>Islas XAML

[Islas XAML](/windows/apps/desktop/modernize/xaml-islands) es un conjunto de componentes para que los desarrolladores usen los nuevos controles de Windows 10 (controles XAML de UWP) en sus aplicaciones WPF, Windows Forms y Win32 nativas actuales (como MFC). Puede tener sus "islas" de controles XAML de UWP dondequiera que desee dentro de las aplicaciones de Win32.

Estas islas XAML son posibles porque la versión 1903 de Windows 10 incluye un conjunto de API que permite hospedar contenido XAML de UWP en ventanas de Win32 mediante controladores de Windows (HWND). Tenga en cuenta que solo las aplicaciones que se ejecutan en Windows 10 1903 y versiones posteriores pueden utilizar islas XAML.

Para que resulte más fácil crear islas XAML para los desarrolladores de Windows Forms y WPF, el kit de herramientas de la comunidad de Windows presenta un conjunto de contenedores de .NET en varios paquetes de NuGet. Estos contenedores son los controles encapsulados y de hospedaje:

- Los controles encapsulados [WebView](/windows/communitytoolkit/controls/wpf-winforms/webview), [WebViewCompatible](/windows/communitytoolkit/controls/wpf-winforms/webviewcompatible), [InkCanvas](/windows/communitytoolkit/controls/wpf-winforms/inkcanvas), [MEDIAPLAYERELEMENT](/windows/communitytoolkit/controls/wpf-winforms/mediaplayerelement)y [MapControl](/windows/communitytoolkit/controls/wpf-winforms/mapcontrol) encapsulan algunos controles XAML de UWP en Windows Forms o controles de WPF, ocultando los conceptos de UWP para esos desarrolladores.
- El control [WindowsXamlHost](/windows/communitytoolkit/controls/wpf-winforms/windowsxamlhost) para Windows Forms y WPF permite que otros controles XAML de UWP no ajustados y controles personalizados se puedan cargar en una isla XAML.

### <a name="access-to-all-windows-10-apis"></a>Acceso a todas las API de Windows 10

Windows 10 tiene una gran cantidad de API disponible para que los desarrolladores trabajen con ella. Estas API proporcionan acceso a una amplia variedad de funciones como autenticación, Bluetooth, citas y contactos. Ahora estas API se exponen a través de .NET Core y proporcionan a los desarrolladores de Windows la oportunidad de crear aplicaciones de escritorio eficaces que aprovechan las funcionalidades presentes en Windows 10.

### <a name="side-by-side-support-and-self-contained-exes"></a>Compatibilidad en paralelo y archivos exe independientes

El modelo de implementación de .NET Core es una de las ventajas más importantes que los desarrolladores de escritorio de Windows experimentarán con .NET Core. La capacidad de instalar .NET Core de forma global proporciona gran parte de la misma instalación central y los beneficios de servicio de .NET Framework, pero no requiere actualizaciones en contexto.

Cuando se lance una nueva versión de .NET Core, puede actualizar cada aplicación en un equipo según sea necesario sin que ello afecte a otras aplicaciones. Las nuevas versiones de .NET Core se instalan en sus propios directorios y existen "en paralelo" entre sí.

Si necesita implementar con aislamiento, puede implementar .NET Core con su aplicación. .NET Core agrupará la aplicación con el tiempo de ejecución de .NET Core como en un único archivo ejecutable.

Estas opciones de implementación fueron solicitadas por los desarrolladores durante mucho tiempo, pero eran difíciles de lograr mediante .NET Framework. La arquitectura modular que usa .NET Core facilita estas opciones de implementación flexibles.

### <a name="performance"></a>Rendimiento

Desde su inicio, dirigido a las cargas de trabajo web y en la nube, .NET Core ha tenido rendimiento conectado en su DNA. El código del lado servidor debe ser lo suficientemente eficaz como para satisfacer los escenarios de gran simultaneidad y las puntuaciones de .NET Core actualmente como la mejor plataforma web de rendimiento en el mercado.

Puede aprovechar estas mejoras de rendimiento al usar .NET Core para compilar la próxima generación de aplicaciones de escritorio.

## <a name="benefits-of-open-source"></a>Ventajas del código abierto

Unas pocas palabras sobre .NET Core que son de código abierto. La creación de una pila multiplataforma es algo complejo que requiere la interacción de equipos especializados en cada una de las plataformas de destino. Este esfuerzo necesita una gran colaboración desde dentro y fuera de Microsoft. Al convertirlo en código abierto y, por tanto, abrirse en la colaboración pública, obtiene el estilo de desarrollo ágil más avanzado, elevando la barra de calidad, ya que los problemas los detecta una comunidad de desarrolladores de gran tamaño y actividad.

Se trata de un factor de éxito clave de .NET Core que seguirá acelerando el plan de desarrollo mencionado anteriormente: para ser la única plataforma de .NET que cualquier desarrollador necesitará para compilar cualquier aplicación.

>[!div class="step-by-step"]
>[Anterior](why-modern-applications.md)
>[Siguiente](migrate-modern-applications.md)
