---
title: Procedimientos de accesibilidad recomendados
description: Obtenga información sobre los procedimientos recomendados de accesibilidad en .NET. Explore el acceso mediante programación, la configuración de usuario, el diseño de la interfaz de usuario visual, la navegación y las interfaces multimodal.
ms.date: 03/30/2017
helpviewer_keywords:
- best practices for accessibility
- accessibility, best practices for
ms.assetid: e6d5cd98-21a3-4b01-999c-fb953556d0e6
ms.openlocfilehash: e2a540678b9f802a3b06a5f3091a7bde33d99739
ms.sourcegitcommit: 38999dc0ec4f7c4404de5ce0951b64c55997d9ab
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/02/2021
ms.locfileid: "99427014"
---
# <a name="accessibility-best-practices"></a>Prácticas recomendadas de accesibilidad

> [!NOTE]
> Este artículo está destinado a .NET Framework desarrolladores que desean usar las clases de automatización de la interfaz de usuario administrada definidas en el <xref:System.Windows.Automation> espacio de nombres. Para obtener la información más reciente sobre la automatización de la interfaz de usuario, consulte [API de automatización de Windows: UI Automation](/windows/win32/winauto/entry-uiauto-win32).

La implementación de los siguientes procedimientos recomendados en los controles o las aplicaciones mejorará su accesibilidad para las personas que utilizan dispositivos de tecnología de asistencia. Muchas de estas prácticas recomendadas se centran en un buen diseño de la interfaz de usuario (IU). Cada procedimiento recomendado incluye información de implementación de controles o aplicaciones Windows Presentation Foundation (WPF). En muchos casos, el trabajo para cumplir estos procedimientos recomendados ya está incluido en los controles de WPF.

<a name="Programmatic_Access"></a>

## <a name="programmatic-access"></a>Acceso mediante programación

El acceso mediante programación implica asegurarse de que todos los elementos de la interfaz de usuario tienen la etiqueta, los valores de propiedad se exponen y se generan los eventos adecuados. En el caso de los controles estándar de WPF, la mayor parte de este trabajo ya se realiza a través de <xref:System.Windows.Automation.Peers.AutomationPeer> . Los controles personalizados requieren trabajo adicional para comprobar que el acceso mediante programación esté implementado correctamente.

<a name="Enable_Programmatic_Access_to_all_UI_Elements_and_Text"></a>

### <a name="enable-programmatic-access-to-all-ui-elements-and-text"></a>Habilitar el acceso mediante programación a todos los elementos de la interfaz de usuario y el texto

Los elementos de la interfaz de usuario (IU) deben habilitar el acceso mediante programación. Si la interfaz de usuario es un control WPF estándar, la compatibilidad con el acceso mediante programación se incluye en el control. Si el control es un control personalizado, un control derivado de un control común o un control derivado de Control, debe comprobar la implementación de <xref:System.Windows.Automation.Peers.AutomationPeer> en las áreas que puedan necesitar modificaciones.

Seguir este procedimiento recomendado permite a los proveedores de tecnología de asistencia identificar y manipular los elementos de la interfaz de usuario del producto.

<a name="Place_Names__Titles_and_Descriptions_on_UI_Objects_"></a>

### <a name="place-names-titles-and-descriptions-on-ui-objects-frames-and-pages"></a>Colocar nombres, títulos y descripciones en objetos de interfaz de usuario, marcos y páginas

Las tecnologías de asistencia, especialmente los lectores de pantalla, utilizan el título para entender la ubicación del marco, el objeto o la página dentro del esquema de navegación. Por lo tanto, el título debe ser descriptivo. Por ejemplo, si el título de una página web es “página web de Microsoft”, será inútil si el usuario navegó hasta un área muy concreta. Los títulos descriptivos son fundamentales para los usuarios ciegos que dependen de los lectores de pantalla. De forma similar, para los controles de WPF, <xref:System.Windows.Automation.AutomationProperties.NameProperty> y <xref:System.Windows.Automation.AutomationProperties.HelpTextProperty> son importantes para los dispositivos de tecnología de asistencia.

Seguir este procedimiento recomendado permite que las tecnologías de asistencia identifiquen y manipulen la interfaz de usuario en controles y aplicaciones de ejemplo.

<a name="Ensure_Programmatic_Events_are_Triggered_by_all_UI"></a>

### <a name="ensure-programmatic-events-are-triggered-by-all-ui-activities"></a>Asegurarse de que todas las actividades de la interfaz de usuario activan eventos mediante programación

Seguir este procedimiento recomendado permite a las tecnologías de asistencia escuchar los cambios en la interfaz de usuario y notificar a los usuarios acerca de estos cambios.

<a name="User_Settings"></a>

## <a name="user-settings"></a>Configuración del usuario

Con el procedimiento recomendado de esta sección, puede asegurarse de que los controles o las aplicaciones no sobrescriban la configuración del usuario.

<a name="Respect_all_System_Wide_Settings_and_do_not_Interfere"></a>

### <a name="respect-all-system-wide-settings-and-do-not-interfere-with-accessibility-functions"></a>Respetar todas las configuraciones de todo el sistema y no interferir con las funciones de accesibilidad

Los usuarios pueden usar el Panel de control para establecer algunos marcadores para todo el sistema. Otras marcas se pueden establecer mediante programación. Esta configuración no debe cambiarse con controles ni aplicaciones. Además, las aplicaciones deben admitir la configuración de accesibilidad de su sistema operativo host.

Seguir este procedimiento recomendado permite a los usuarios establecer la configuración de accesibilidad y saber que las aplicaciones no cambiarán esa configuración.

<a name="Visual_UI_Design"></a>

## <a name="visual-ui-design"></a>Diseño visual de la interfaz de usuario

Los procedimientos recomendados de esta sección garantizan que los controles o las aplicaciones usen el color e imágenes de forma eficaz y puedan ser utilizados por las tecnologías de asistencia.

<a name="Don_t_Hard_Code_Colors"></a>

### <a name="dont-hard-code-colors"></a>No codificar los colores de forma rígida

Es posible que las personas que son daltónicas, tienen poca visión o usan una pantalla en blanco y negro no puedan utilizar las aplicaciones con colores codificados de forma rígida.

Seguir este procedimiento recomendado permite a los usuarios ajustar las combinaciones de colores en función de sus necesidades individuales.

<a name="Support_High_Contrast_and_all_System_Display_Attributes"></a>

### <a name="support-high-contrast-and-all-system-display-attributes"></a>Compatibilidad con el contraste alto y todos los atributos de visualización del sistema

Las aplicaciones no deben interrumpir ni deshabilitar la configuración de contraste seleccionada por el usuario para todo el sistema, así como las selecciones de color u otros atributos y configuraciones de visualización para todo el sistema. La configuración del sistema adoptada por un usuario mejora la accesibilidad de las aplicaciones, por lo que las aplicaciones no deben deshabilitarla ni ignorarla. El color se debe utilizar en su combinación correcta de primer plano y fondo para proporcionar el contraste apropiado. No mezcle colores no relacionados ni invierten los colores.

Muchos usuarios necesitan combinaciones concretas de contraste alto, como texto blanco sobre un fondo negro. Si se dibujan invertidas, por ejemplo, como texto negro sobre un fondo blanco, esto hará que el fondo se superponga al primer plano y puede dificultar la lectura de algunos usuarios.

<a name="Ensure_all_UI_Correctly_Scales_by_any_DPI_Setting"></a>

### <a name="ensure-all-ui-correctly-scales-by-any-dpi-setting"></a>Asegurarse de que toda la interfaz de usuario se escale correctamente con cualquier configuración de PPP

Asegúrese de que toda la interfaz de usuario se puede escalar correctamente con cualquier valor de puntos por pulgada (PPP). Además, asegúrese de que los elementos de la interfaz de usuario se ajustan en una pantalla de 1024 x 768 con 120 puntos por pulgada (PPP).

<a name="Navigation"></a>

## <a name="navigation"></a>Navegación

Los procedimientos recomendados en esta sección abarcan la navegación de los controles y las aplicaciones.

<a name="Provide_Keyboard_Interface_for_all_UI_Elements"></a>

### <a name="provide-keyboard-interface-for-all-ui-elements"></a>Proporcionar la interfaz de teclado a todos los elementos de la interfaz de usuario

Las tabulaciones, especialmente cuando se planean cuidadosamente, proporcionan a los usuarios otra manera de navegar por la interfaz de usuario.

Las aplicaciones deben proporcionar las interfaces de teclado siguientes:

- tabulaciones para todos los controles con los que pueda interactuar el usuario, como botones, vínculos o cuadros de lista
- orden de tabulación lógico

<a name="Show_the_Keyboard_Focus"></a>

### <a name="show-the-keyboard-focus"></a>Mostrar el foco del teclado

Los usuarios necesitan saber qué objeto tiene el foco del teclado para poder prever el efecto de las pulsaciones de teclas. Para resaltar el foco del teclado, utilice colores, fuentes o gráficos como rectángulos o ampliaciones. Para resaltar audiblemente el foco del teclado, cambie el volumen, el tono o la calidad tonal.

Para evitar confusiones, las aplicaciones deben ocultar todos los indicadores de foco visuales y atenuar las selecciones que se encuentran en las ventanas, o los paneles, inactivos.

Las aplicaciones deben hacer lo siguiente con el foco del teclado:

- un elemento deberá tener siempre el foco del teclado
- el foco del teclado debe ser visible y obvio
- las selecciones y/o los elementos donde se encuentra el foco deben aparecer resaltados visualmente

<a name="Support_Navigation_Standards_and_Powerful_Navigation"></a>

### <a name="support-navigation-standards-and-powerful-navigation-schemes"></a>Compatibilidad con los estándares de navegación y esquemas de navegación eficaces

Distintos aspectos de la navegación con el teclado proporcionan diferentes maneras de navegar por la interfaz de usuario.

Las aplicaciones deben proporcionar las interfaces de teclado siguientes:

- teclas de método abreviado y teclas de acceso subrayadas para todos los comandos, menús y controles
- métodos abreviados de teclado para los vínculos importantes
- todos los elementos de menú deben tener una tecla de acceso, todos los botones deben tener teclas de aceleración y todos los comandos deben tener una tecla de aceleración.

<a name="Do_not_let_Mouse_Location_Interfere_with_Keyboard"></a>

### <a name="do-not-let-mouse-location-interfere-with-keyboard-navigation"></a>No dejar que la ubicación del mouse interfiera con la navegación mediante el teclado

La ubicación del mouse no debe interferir con la navegación mediante el teclado. Por ejemplo, si se coloca el mouse en algún lugar y el usuario navega con el teclado, no debería producirse un clic del mouse a menos que lo inicie el usuario.

<a name="Multimodal_Interface"></a>

## <a name="multimodal-interface"></a>Interfaz multimodal

Los procedimientos recomendados de esta sección garantizan que la interfaz de usuario de la aplicación incluya alternativas para los elementos visuales.

<a name="Provide_User_Selectable_Equivalents_for_Non_Text"></a>

### <a name="provide-user-selectable-equivalents-for-non-text-elements"></a>Proporcionar equivalentes seleccionables por el usuario para los elementos no textuales

Para cada elemento no textual, proporcione un equivalente seleccionable por el usuario para el texto, transcripciones o descripciones de audio, como texto alternativo, títulos o comentarios visuales.

<!-- markdownlint-disable DOCSMD011 -->
Los elementos que no son de texto cubren una amplia gama de elementos de la interfaz de usuario, como imágenes, regiones de mapa de imagen, animaciones, applets, Marcos, scripts, botones gráficos, sonidos, archivos de audio independientes y vídeo. Los elementos no textuales son importantes cuando contienen información visual, voz o información de audio general a la que el usuario necesita acceder para entender el contenido de la interfaz de usuario.

<a name="Use_Color_but_also_Provide_Alternatives_to_Color"></a>

### <a name="use-color-but-also-provide-alternatives-to-color"></a>Usar color, pero proporcionar también alternativas al color

Use el color para mejorar, enfatizar o reiterar la información que se muestra por otros medios, pero no comunique la información con el color exclusivamente. Los usuarios daltónicos o con pantallas monocromáticas necesitan alternativas al color.

<a name="Use_Standard_Input_APIs_with_Devices_Independent"></a>

### <a name="use-standard-input-apis-with-device-independent-calls"></a>Usar la API de entrada estándar con llamadas independientes del dispositivo

Las llamadas independientes del dispositivo garantizan la igualdad de las características del teclado y del mouse, a la vez que proporcionan una tecnología de asistencia con la información necesaria sobre la interfaz de usuario.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Automation.Peers>
- [NumericUpDown Custom Control with Theme and UI Automation Support Sample (Ejemplo de un control personalizado NumericUpDown y compatibilidad para Automatización de la interfaz de usuario)](</previous-versions/dotnet/netframework-3.5/ms771573(v=vs.90)>)
- [Directrices para el diseño de la interfaz de usuario de teclado](/previous-versions/windows/desktop/dnacc/guidelines-for-keyboard-user-interface-design)
