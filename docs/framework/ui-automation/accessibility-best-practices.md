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
# <a name="accessibility-best-practices"></a><span data-ttu-id="4ef6e-104">Prácticas recomendadas de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="4ef6e-104">Accessibility best practices</span></span>

> [!NOTE]
> <span data-ttu-id="4ef6e-105">Este artículo está destinado a .NET Framework desarrolladores que desean usar las clases de automatización de la interfaz de usuario administrada definidas en el <xref:System.Windows.Automation> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-105">This article is intended for .NET Framework developers who want to use the managed UI Automation classes defined in the <xref:System.Windows.Automation> namespace.</span></span> <span data-ttu-id="4ef6e-106">Para obtener la información más reciente sobre la automatización de la interfaz de usuario, consulte [API de automatización de Windows: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span><span class="sxs-lookup"><span data-stu-id="4ef6e-106">For the latest information about UI Automation, see [Windows Automation API: UI Automation](/windows/win32/winauto/entry-uiauto-win32).</span></span>

<span data-ttu-id="4ef6e-107">La implementación de los siguientes procedimientos recomendados en los controles o las aplicaciones mejorará su accesibilidad para las personas que utilizan dispositivos de tecnología de asistencia.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-107">Implementing the following best practices in controls or applications will improve their accessibility for people who use assistive technology devices.</span></span> <span data-ttu-id="4ef6e-108">Muchas de estas prácticas recomendadas se centran en un buen diseño de la interfaz de usuario (IU).</span><span class="sxs-lookup"><span data-stu-id="4ef6e-108">Many of these best practices focus on good user interface (UI) design.</span></span> <span data-ttu-id="4ef6e-109">Cada procedimiento recomendado incluye información de implementación de controles o aplicaciones Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="4ef6e-109">Each best practice includes implementation information for Windows Presentation Foundation (WPF) controls or applications.</span></span> <span data-ttu-id="4ef6e-110">En muchos casos, el trabajo para cumplir estos procedimientos recomendados ya está incluido en los controles de WPF.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-110">In many cases, the work to meet these best practices is already included in WPF controls.</span></span>

<a name="Programmatic_Access"></a>

## <a name="programmatic-access"></a><span data-ttu-id="4ef6e-111">Acceso mediante programación</span><span class="sxs-lookup"><span data-stu-id="4ef6e-111">Programmatic Access</span></span>

<span data-ttu-id="4ef6e-112">El acceso mediante programación implica asegurarse de que todos los elementos de la interfaz de usuario tienen la etiqueta, los valores de propiedad se exponen y se generan los eventos adecuados.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-112">Programmatic access involves ensuring that all UI elements are labeled, property values are exposed, and appropriate events are raised.</span></span> <span data-ttu-id="4ef6e-113">En el caso de los controles estándar de WPF, la mayor parte de este trabajo ya se realiza a través de <xref:System.Windows.Automation.Peers.AutomationPeer> .</span><span class="sxs-lookup"><span data-stu-id="4ef6e-113">For standard WPF controls, most of this work is already done through <xref:System.Windows.Automation.Peers.AutomationPeer>.</span></span> <span data-ttu-id="4ef6e-114">Los controles personalizados requieren trabajo adicional para comprobar que el acceso mediante programación esté implementado correctamente.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-114">Custom controls require additional work to ensure that programmatic access is correctly implemented.</span></span>

<a name="Enable_Programmatic_Access_to_all_UI_Elements_and_Text"></a>

### <a name="enable-programmatic-access-to-all-ui-elements-and-text"></a><span data-ttu-id="4ef6e-115">Habilitar el acceso mediante programación a todos los elementos de la interfaz de usuario y el texto</span><span class="sxs-lookup"><span data-stu-id="4ef6e-115">Enable Programmatic Access to all UI Elements and Text</span></span>

<span data-ttu-id="4ef6e-116">Los elementos de la interfaz de usuario (IU) deben habilitar el acceso mediante programación.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-116">User interface (UI) elements should enable programmatic access.</span></span> <span data-ttu-id="4ef6e-117">Si la interfaz de usuario es un control WPF estándar, la compatibilidad con el acceso mediante programación se incluye en el control.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-117">If the UI is a standard WPF control, support for programmatic access is included in the control.</span></span> <span data-ttu-id="4ef6e-118">Si el control es un control personalizado, un control derivado de un control común o un control derivado de Control, debe comprobar la implementación de <xref:System.Windows.Automation.Peers.AutomationPeer> en las áreas que puedan necesitar modificaciones.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-118">If the control is a custom control – a control that has been subclassed from a common control or a control that has been subclassed from Control – then you must check the <xref:System.Windows.Automation.Peers.AutomationPeer> implementation for areas that may need modification.</span></span>

<span data-ttu-id="4ef6e-119">Seguir este procedimiento recomendado permite a los proveedores de tecnología de asistencia identificar y manipular los elementos de la interfaz de usuario del producto.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-119">Following this best practice allows assistive technology vendors to identify and manipulate elements of your product's UI.</span></span>

<a name="Place_Names__Titles_and_Descriptions_on_UI_Objects_"></a>

### <a name="place-names-titles-and-descriptions-on-ui-objects-frames-and-pages"></a><span data-ttu-id="4ef6e-120">Colocar nombres, títulos y descripciones en objetos de interfaz de usuario, marcos y páginas</span><span class="sxs-lookup"><span data-stu-id="4ef6e-120">Place Names, Titles, and Descriptions on UI Objects, Frames, and Pages</span></span>

<span data-ttu-id="4ef6e-121">Las tecnologías de asistencia, especialmente los lectores de pantalla, utilizan el título para entender la ubicación del marco, el objeto o la página dentro del esquema de navegación.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-121">Assistive technologies, especially screen readers, use the title to understand the location of the frame, object, or page in the navigation scheme.</span></span> <span data-ttu-id="4ef6e-122">Por lo tanto, el título debe ser descriptivo.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-122">Therefore, the title must be descriptive.</span></span> <span data-ttu-id="4ef6e-123">Por ejemplo, si el título de una página web es “página web de Microsoft”, será inútil si el usuario navegó hasta un área muy concreta.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-123">For example, a Web page title of "Microsoft Web Page" is useless if the user has navigated deeply into some particular area.</span></span> <span data-ttu-id="4ef6e-124">Los títulos descriptivos son fundamentales para los usuarios ciegos que dependen de los lectores de pantalla.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-124">A descriptive title is critical for users who are blind and depend on screen readers.</span></span> <span data-ttu-id="4ef6e-125">De forma similar, para los controles de WPF, <xref:System.Windows.Automation.AutomationProperties.NameProperty> y <xref:System.Windows.Automation.AutomationProperties.HelpTextProperty> son importantes para los dispositivos de tecnología de asistencia.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-125">Similarly, for WPF controls, <xref:System.Windows.Automation.AutomationProperties.NameProperty> and <xref:System.Windows.Automation.AutomationProperties.HelpTextProperty> are important for assistive technology devices.</span></span>

<span data-ttu-id="4ef6e-126">Seguir este procedimiento recomendado permite que las tecnologías de asistencia identifiquen y manipulen la interfaz de usuario en controles y aplicaciones de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-126">Following this best practice allows assistive technologies to identify and manipulate UI in sample controls and applications.</span></span>

<a name="Ensure_Programmatic_Events_are_Triggered_by_all_UI"></a>

### <a name="ensure-programmatic-events-are-triggered-by-all-ui-activities"></a><span data-ttu-id="4ef6e-127">Asegurarse de que todas las actividades de la interfaz de usuario activan eventos mediante programación</span><span class="sxs-lookup"><span data-stu-id="4ef6e-127">Ensure Programmatic Events Are Triggered by All UI Activities</span></span>

<span data-ttu-id="4ef6e-128">Seguir este procedimiento recomendado permite a las tecnologías de asistencia escuchar los cambios en la interfaz de usuario y notificar a los usuarios acerca de estos cambios.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-128">Following this best practice allows assistive technologies to listen for changes in the UI and notify the user about these changes.</span></span>

<a name="User_Settings"></a>

## <a name="user-settings"></a><span data-ttu-id="4ef6e-129">Configuración del usuario</span><span class="sxs-lookup"><span data-stu-id="4ef6e-129">User Settings</span></span>

<span data-ttu-id="4ef6e-130">Con el procedimiento recomendado de esta sección, puede asegurarse de que los controles o las aplicaciones no sobrescriban la configuración del usuario.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-130">The best practice in this section ensures that controls or applications do not override user settings.</span></span>

<a name="Respect_all_System_Wide_Settings_and_do_not_Interfere"></a>

### <a name="respect-all-system-wide-settings-and-do-not-interfere-with-accessibility-functions"></a><span data-ttu-id="4ef6e-131">Respetar todas las configuraciones de todo el sistema y no interferir con las funciones de accesibilidad</span><span class="sxs-lookup"><span data-stu-id="4ef6e-131">Respect All System-Wide Settings and Do Not Interfere with Accessibility Functions</span></span>

<span data-ttu-id="4ef6e-132">Los usuarios pueden usar el Panel de control para establecer algunos marcadores para todo el sistema. Otras marcas se pueden establecer mediante programación.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-132">Users can use the Control Panel to set some system-wide flags; other flags can be set programmatically.</span></span> <span data-ttu-id="4ef6e-133">Esta configuración no debe cambiarse con controles ni aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-133">These settings should not be changed by controls or applications.</span></span> <span data-ttu-id="4ef6e-134">Además, las aplicaciones deben admitir la configuración de accesibilidad de su sistema operativo host.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-134">Also, applications must support the accessibility settings of their host operating system.</span></span>

<span data-ttu-id="4ef6e-135">Seguir este procedimiento recomendado permite a los usuarios establecer la configuración de accesibilidad y saber que las aplicaciones no cambiarán esa configuración.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-135">Following this best practice allows users to set accessibility settings and know that those settings will not be changed by applications.</span></span>

<a name="Visual_UI_Design"></a>

## <a name="visual-ui-design"></a><span data-ttu-id="4ef6e-136">Diseño visual de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="4ef6e-136">Visual UI Design</span></span>

<span data-ttu-id="4ef6e-137">Los procedimientos recomendados de esta sección garantizan que los controles o las aplicaciones usen el color e imágenes de forma eficaz y puedan ser utilizados por las tecnologías de asistencia.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-137">Best Practices in this section ensure that controls or applications use color and images effectively and are able to be used by Assistive technologies.</span></span>

<a name="Don_t_Hard_Code_Colors"></a>

### <a name="dont-hard-code-colors"></a><span data-ttu-id="4ef6e-138">No codificar los colores de forma rígida</span><span class="sxs-lookup"><span data-stu-id="4ef6e-138">Don't Hard-Code Colors</span></span>

<span data-ttu-id="4ef6e-139">Es posible que las personas que son daltónicas, tienen poca visión o usan una pantalla en blanco y negro no puedan utilizar las aplicaciones con colores codificados de forma rígida.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-139">People who are color blind, have low vision, or are using a black and white screen might not be able to use applications with hard-coded colors.</span></span>

<span data-ttu-id="4ef6e-140">Seguir este procedimiento recomendado permite a los usuarios ajustar las combinaciones de colores en función de sus necesidades individuales.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-140">Following this best practice allows users to adjust color combinations based on individual needs.</span></span>

<a name="Support_High_Contrast_and_all_System_Display_Attributes"></a>

### <a name="support-high-contrast-and-all-system-display-attributes"></a><span data-ttu-id="4ef6e-141">Compatibilidad con el contraste alto y todos los atributos de visualización del sistema</span><span class="sxs-lookup"><span data-stu-id="4ef6e-141">Support High Contrast and all System Display Attributes</span></span>

<span data-ttu-id="4ef6e-142">Las aplicaciones no deben interrumpir ni deshabilitar la configuración de contraste seleccionada por el usuario para todo el sistema, así como las selecciones de color u otros atributos y configuraciones de visualización para todo el sistema.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-142">Applications should not disrupt or disable user-selected, system-wide contrast settings, color selections, or other system-wide display settings and attributes.</span></span> <span data-ttu-id="4ef6e-143">La configuración del sistema adoptada por un usuario mejora la accesibilidad de las aplicaciones, por lo que las aplicaciones no deben deshabilitarla ni ignorarla.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-143">System-wide settings adopted by a user enhance the accessibility of applications, so they should not be disabled or disregarded by applications.</span></span> <span data-ttu-id="4ef6e-144">El color se debe utilizar en su combinación correcta de primer plano y fondo para proporcionar el contraste apropiado.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-144">Color should be used in their correct foreground-on-background combination to provide proper contrast.</span></span> <span data-ttu-id="4ef6e-145">No mezcle colores no relacionados ni invierten los colores.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-145">Don't mix unrelated colors, and don't reverse colors.</span></span>

<span data-ttu-id="4ef6e-146">Muchos usuarios necesitan combinaciones concretas de contraste alto, como texto blanco sobre un fondo negro.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-146">Many users require specific high-contrast combinations, such as white text on a black background.</span></span> <span data-ttu-id="4ef6e-147">Si se dibujan invertidas, por ejemplo, como texto negro sobre un fondo blanco, esto hará que el fondo se superponga al primer plano y puede dificultar la lectura de algunos usuarios.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-147">Drawing these reversed, as black text on a white background causes the background to bleed over the foreground and can make reading difficult for some users.</span></span>

<a name="Ensure_all_UI_Correctly_Scales_by_any_DPI_Setting"></a>

### <a name="ensure-all-ui-correctly-scales-by-any-dpi-setting"></a><span data-ttu-id="4ef6e-148">Asegurarse de que toda la interfaz de usuario se escale correctamente con cualquier configuración de PPP</span><span class="sxs-lookup"><span data-stu-id="4ef6e-148">Ensure All UI Correctly Scales by Any DPI Setting</span></span>

<span data-ttu-id="4ef6e-149">Asegúrese de que toda la interfaz de usuario se puede escalar correctamente con cualquier valor de puntos por pulgada (PPP).</span><span class="sxs-lookup"><span data-stu-id="4ef6e-149">Ensure that all UI can correctly scale by any dots per inch (dpi) setting.</span></span> <span data-ttu-id="4ef6e-150">Además, asegúrese de que los elementos de la interfaz de usuario se ajustan en una pantalla de 1024 x 768 con 120 puntos por pulgada (PPP).</span><span class="sxs-lookup"><span data-stu-id="4ef6e-150">Also, ensure that UI elements fit in a screen of 1024 x 768 with 120 dots per inch (dpi).</span></span>

<a name="Navigation"></a>

## <a name="navigation"></a><span data-ttu-id="4ef6e-151">Navegación</span><span class="sxs-lookup"><span data-stu-id="4ef6e-151">Navigation</span></span>

<span data-ttu-id="4ef6e-152">Los procedimientos recomendados en esta sección abarcan la navegación de los controles y las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-152">Best Practices in this section ensure that navigation has been addressed for controls and applications.</span></span>

<a name="Provide_Keyboard_Interface_for_all_UI_Elements"></a>

### <a name="provide-keyboard-interface-for-all-ui-elements"></a><span data-ttu-id="4ef6e-153">Proporcionar la interfaz de teclado a todos los elementos de la interfaz de usuario</span><span class="sxs-lookup"><span data-stu-id="4ef6e-153">Provide Keyboard Interface for All UI Elements</span></span>

<span data-ttu-id="4ef6e-154">Las tabulaciones, especialmente cuando se planean cuidadosamente, proporcionan a los usuarios otra manera de navegar por la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-154">Tab stops, especially when carefully planned, give users another way to navigate the UI.</span></span>

<span data-ttu-id="4ef6e-155">Las aplicaciones deben proporcionar las interfaces de teclado siguientes:</span><span class="sxs-lookup"><span data-stu-id="4ef6e-155">Applications should provide the following keyboard interfaces:</span></span>

- <span data-ttu-id="4ef6e-156">tabulaciones para todos los controles con los que pueda interactuar el usuario, como botones, vínculos o cuadros de lista</span><span class="sxs-lookup"><span data-stu-id="4ef6e-156">tab stops for all controls that the user can interact with, such as buttons, links, or list boxes</span></span>
- <span data-ttu-id="4ef6e-157">orden de tabulación lógico</span><span class="sxs-lookup"><span data-stu-id="4ef6e-157">logical tab order</span></span>

<a name="Show_the_Keyboard_Focus"></a>

### <a name="show-the-keyboard-focus"></a><span data-ttu-id="4ef6e-158">Mostrar el foco del teclado</span><span class="sxs-lookup"><span data-stu-id="4ef6e-158">Show the Keyboard Focus</span></span>

<span data-ttu-id="4ef6e-159">Los usuarios necesitan saber qué objeto tiene el foco del teclado para poder prever el efecto de las pulsaciones de teclas.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-159">Users need to know which object has the keyboard focus so that they can anticipate the effect of their keystrokes.</span></span> <span data-ttu-id="4ef6e-160">Para resaltar el foco del teclado, utilice colores, fuentes o gráficos como rectángulos o ampliaciones.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-160">To highlight the keyboard focus, use colors, fonts, or graphics such as rectangles or magnification.</span></span> <span data-ttu-id="4ef6e-161">Para resaltar audiblemente el foco del teclado, cambie el volumen, el tono o la calidad tonal.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-161">To audibly highlight the keyboard focus, change the volume, pitch, or tonal quality.</span></span>

<span data-ttu-id="4ef6e-162">Para evitar confusiones, las aplicaciones deben ocultar todos los indicadores de foco visuales y atenuar las selecciones que se encuentran en las ventanas, o los paneles, inactivos.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-162">To avoid confusion, applications should hide all visual focus indicators and dim selections that are located in inactive windows (or panes).</span></span>

<span data-ttu-id="4ef6e-163">Las aplicaciones deben hacer lo siguiente con el foco del teclado:</span><span class="sxs-lookup"><span data-stu-id="4ef6e-163">Applications should do the following with keyboard focus:</span></span>

- <span data-ttu-id="4ef6e-164">un elemento deberá tener siempre el foco del teclado</span><span class="sxs-lookup"><span data-stu-id="4ef6e-164">one item should always have keyboard focus</span></span>
- <span data-ttu-id="4ef6e-165">el foco del teclado debe ser visible y obvio</span><span class="sxs-lookup"><span data-stu-id="4ef6e-165">keyboard focus should be visible and obvious</span></span>
- <span data-ttu-id="4ef6e-166">las selecciones y/o los elementos donde se encuentra el foco deben aparecer resaltados visualmente</span><span class="sxs-lookup"><span data-stu-id="4ef6e-166">selections and/or focused items should be visually highlighted</span></span>

<a name="Support_Navigation_Standards_and_Powerful_Navigation"></a>

### <a name="support-navigation-standards-and-powerful-navigation-schemes"></a><span data-ttu-id="4ef6e-167">Compatibilidad con los estándares de navegación y esquemas de navegación eficaces</span><span class="sxs-lookup"><span data-stu-id="4ef6e-167">Support Navigation Standards and Powerful Navigation Schemes</span></span>

<span data-ttu-id="4ef6e-168">Distintos aspectos de la navegación con el teclado proporcionan diferentes maneras de navegar por la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-168">Different aspects of keyboard navigation provide different ways for users to navigate the UI.</span></span>

<span data-ttu-id="4ef6e-169">Las aplicaciones deben proporcionar las interfaces de teclado siguientes:</span><span class="sxs-lookup"><span data-stu-id="4ef6e-169">Applications should provide the following keyboard interfaces:</span></span>

- <span data-ttu-id="4ef6e-170">teclas de método abreviado y teclas de acceso subrayadas para todos los comandos, menús y controles</span><span class="sxs-lookup"><span data-stu-id="4ef6e-170">shortcut keys and underlined access keys for all commands, menus, and controls</span></span>
- <span data-ttu-id="4ef6e-171">métodos abreviados de teclado para los vínculos importantes</span><span class="sxs-lookup"><span data-stu-id="4ef6e-171">keyboard shortcuts to important links</span></span>
- <span data-ttu-id="4ef6e-172">todos los elementos de menú deben tener una tecla de acceso, todos los botones deben tener teclas de aceleración y todos los comandos deben tener una tecla de aceleración.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-172">all menu items have an access key; all buttons have accelerator keys, all commands have an accelerator key.</span></span>

<a name="Do_not_let_Mouse_Location_Interfere_with_Keyboard"></a>

### <a name="do-not-let-mouse-location-interfere-with-keyboard-navigation"></a><span data-ttu-id="4ef6e-173">No dejar que la ubicación del mouse interfiera con la navegación mediante el teclado</span><span class="sxs-lookup"><span data-stu-id="4ef6e-173">Do Not Let Mouse Location Interfere with Keyboard Navigation</span></span>

<span data-ttu-id="4ef6e-174">La ubicación del mouse no debe interferir con la navegación mediante el teclado.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-174">Mouse location should not interfere with keyboard navigation.</span></span> <span data-ttu-id="4ef6e-175">Por ejemplo, si se coloca el mouse en algún lugar y el usuario navega con el teclado, no debería producirse un clic del mouse a menos que lo inicie el usuario.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-175">For example, if the mouse is positioned some place and the user is navigating with the keyboard, a mouse click should not happen unless initiated by the user.</span></span>

<a name="Multimodal_Interface"></a>

## <a name="multimodal-interface"></a><span data-ttu-id="4ef6e-176">Interfaz multimodal</span><span class="sxs-lookup"><span data-stu-id="4ef6e-176">Multimodal Interface</span></span>

<span data-ttu-id="4ef6e-177">Los procedimientos recomendados de esta sección garantizan que la interfaz de usuario de la aplicación incluya alternativas para los elementos visuales.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-177">Best Practices in this section ensure that application UI includes alternatives for visual elements.</span></span>

<a name="Provide_User_Selectable_Equivalents_for_Non_Text"></a>

### <a name="provide-user-selectable-equivalents-for-non-text-elements"></a><span data-ttu-id="4ef6e-178">Proporcionar equivalentes seleccionables por el usuario para los elementos no textuales</span><span class="sxs-lookup"><span data-stu-id="4ef6e-178">Provide User-Selectable Equivalents for Non-Text Elements</span></span>

<span data-ttu-id="4ef6e-179">Para cada elemento no textual, proporcione un equivalente seleccionable por el usuario para el texto, transcripciones o descripciones de audio, como texto alternativo, títulos o comentarios visuales.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-179">For each non-text element, provide a user-selectable equivalent for text, transcripts, or audio descriptions, such as alt text, captions, or visual feedback.</span></span>

<!-- markdownlint-disable DOCSMD011 -->
<span data-ttu-id="4ef6e-180">Los elementos que no son de texto cubren una amplia gama de elementos de la interfaz de usuario, como imágenes, regiones de mapa de imagen, animaciones, applets, Marcos, scripts, botones gráficos, sonidos, archivos de audio independientes y vídeo.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-180">Non-text elements cover a wide range of UI elements including: images, image map regions, animations, applets, frames, scripts, graphical buttons, sounds, stand-alone audio files, and video.</span></span> <span data-ttu-id="4ef6e-181">Los elementos no textuales son importantes cuando contienen información visual, voz o información de audio general a la que el usuario necesita acceder para entender el contenido de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-181">Non-text elements are important when they contain visual information, speech, or general audio information that the user needs access to in order to understand the content of the UI.</span></span>

<a name="Use_Color_but_also_Provide_Alternatives_to_Color"></a>

### <a name="use-color-but-also-provide-alternatives-to-color"></a><span data-ttu-id="4ef6e-182">Usar color, pero proporcionar también alternativas al color</span><span class="sxs-lookup"><span data-stu-id="4ef6e-182">Use Color but Also Provide Alternatives to Color</span></span>

<span data-ttu-id="4ef6e-183">Use el color para mejorar, enfatizar o reiterar la información que se muestra por otros medios, pero no comunique la información con el color exclusivamente.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-183">Use color to enhance, emphasize, or reiterate information shown by other means, but do not communicate information by using color alone.</span></span> <span data-ttu-id="4ef6e-184">Los usuarios daltónicos o con pantallas monocromáticas necesitan alternativas al color.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-184">Users who are color blind or have a monochrome display need alternatives to color.</span></span>

<a name="Use_Standard_Input_APIs_with_Devices_Independent"></a>

### <a name="use-standard-input-apis-with-device-independent-calls"></a><span data-ttu-id="4ef6e-185">Usar la API de entrada estándar con llamadas independientes del dispositivo</span><span class="sxs-lookup"><span data-stu-id="4ef6e-185">Use Standard Input APIs with Device-Independent Calls</span></span>

<span data-ttu-id="4ef6e-186">Las llamadas independientes del dispositivo garantizan la igualdad de las características del teclado y del mouse, a la vez que proporcionan una tecnología de asistencia con la información necesaria sobre la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="4ef6e-186">Device-independent calls ensure keyboard and mouse feature equality, while providing assistive technology with needed information about the UI.</span></span>

## <a name="see-also"></a><span data-ttu-id="4ef6e-187">Vea también</span><span class="sxs-lookup"><span data-stu-id="4ef6e-187">See also</span></span>

- <xref:System.Windows.Automation.Peers>
- <span data-ttu-id="4ef6e-188">[NumericUpDown Custom Control with Theme and UI Automation Support Sample (Ejemplo de un control personalizado NumericUpDown y compatibilidad para Automatización de la interfaz de usuario)](</previous-versions/dotnet/netframework-3.5/ms771573(v=vs.90)>)</span><span class="sxs-lookup"><span data-stu-id="4ef6e-188">[NumericUpDown Custom Control with Theme and UI Automation Support Sample](</previous-versions/dotnet/netframework-3.5/ms771573(v=vs.90)>)</span></span>
- [<span data-ttu-id="4ef6e-189">Directrices para el diseño de la interfaz de usuario de teclado</span><span class="sxs-lookup"><span data-stu-id="4ef6e-189">Guidelines for Keyboard User Interface Design</span></span>](/previous-versions/windows/desktop/dnacc/guidelines-for-keyboard-user-interface-design)
