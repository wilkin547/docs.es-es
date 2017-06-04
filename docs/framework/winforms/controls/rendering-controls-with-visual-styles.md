---
title: "Representar controles con estilos visuales | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "aspecto profesional, representar controles de Windows Forms"
  - "temas, estilos visuales de XP en Windows Forms"
  - "controles personalizados [Windows Forms], representación"
  - "controles personalizados [Windows Forms], dibujos"
  - "temas visuales, representar controles de Windows Forms"
  - "controles de usuario [Windows Forms], dibujos"
  - "estilos visuales, representar controles de Windows Forms"
ms.assetid: a5b178ba-610e-46c4-a6c0-509c0886a744
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# Representar controles con estilos visuales
[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] proporciona compatibilidad para representar controles y otros elementos de la interfaz de usuario \(IU\) de Windows usando estilos visuales en los sistemas operativos compatibles. En este tema se tratan los distintos niveles de compatibilidad de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] para representar controles y otros elementos de IU con el estilo visual actual del sistema operativo.  
  
## Clases de representación de los controles comunes  
 La representación de un control hace referencia al hecho de dibujar la interfaz de usuario de un control. El espacio de nombres <xref:System.Windows.Forms?displayProperty=fullName> proporciona la clase <xref:System.Windows.Forms.ControlPaint> para representar algunos controles comunes de Windows Forms, aunque esta clase dibuja controles en el estilo clásico de Windows, lo que puede dificultar la tarea de mantener una experiencia de IU coherente al dibujar controles personalizados en aplicaciones que tienen habilitados estilos visuales.  
  
 [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)] incluye las clases del espacio de nombres <xref:System.Windows.Forms?displayProperty=fullName> que representan las partes y los estados de los controles comunes con los estilos visuales. Cada una de estas clases incluye métodos `static` para dibujar el control o las partes del control en un estado particular con el estilo visual actual del sistema operativo.  
  
 Algunas de estas clases están diseñadas para dibujar el control relacionado tanto si los estilos visuales están disponibles como si no lo están. Si los estilos visuales están habilitados, los miembros de clase dibujarán el control relacionado con estilos visuales. Si no lo están, los miembros de clase dibujarán el control en el estilo clásico de Windows. Estas clases incluyen:  
  
-   <xref:System.Windows.Forms.ButtonRenderer>  
  
-   <xref:System.Windows.Forms.CheckBoxRenderer>  
  
-   <xref:System.Windows.Forms.GroupBoxRenderer>  
  
-   <xref:System.Windows.Forms.RadioButtonRenderer>  
  
 El resto de las clases solo pueden dibujar el control relacionado si los estilos visuales están disponibles; además, sus miembros generarán una excepción si los estilos visuales están deshabilitados. Estas clases incluyen:  
  
-   <xref:System.Windows.Forms.ComboBoxRenderer>  
  
-   <xref:System.Windows.Forms.ProgressBarRenderer>  
  
-   <xref:System.Windows.Forms.ScrollBarRenderer>  
  
-   <xref:System.Windows.Forms.TabRenderer>  
  
-   <xref:System.Windows.Forms.TextBoxRenderer>  
  
-   <xref:System.Windows.Forms.TrackBarRenderer>  
  
 Para obtener más información sobre cómo usar estas clases para dibujar un control, consulte [Cómo: Utilizar una clase de representación de controles](../../../../docs/framework/winforms/controls/how-to-use-a-control-rendering-class.md).  
  
## Clases de representación y de elementos de estilos visuales  
 El espacio de nombres <xref:System.Windows.Forms.VisualStyles?displayProperty=fullName> incluye clases que se pueden usar para dibujar y obtener información sobre cualquier control o elemento de IU que sea compatible con los estilos visuales. Los controles compatibles incluyen controles comunes que tienen una clase de representación en el espacio de nombres <xref:System.Windows.Forms?displayProperty=fullName> \(consulte la sección anterior\), así como otros controles, como los controles de pestaña y los controles rebar. Otros elementos de IU compatibles incluyen las partes del menú **Inicio**, la barra de tareas y el área de no cliente de Windows.  
  
 Las clases principales del espacio de nombres <xref:System.Windows.Forms.VisualStyles?displayProperty=fullName> son <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> y <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer>.<xref:System.Windows.Forms.VisualStyles.VisualStyleElement> es una clase básica para identificar cualquier control o elemento de IU compatible con los estilos visuales. Además de <xref:System.Windows.Forms.VisualStyles.VisualStyleElement>, el espacio de nombres <xref:System.Windows.Forms.VisualStyles?displayProperty=fullName> incluye muchas clases anidadas de <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> con propiedades `static` que devuelven una clase <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> para cada estado de un control, parte de control u otro elemento de IU compatible con los estilos visuales.  
  
 <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> proporciona los métodos necesarios para dibujar y obtener información sobre cada clase <xref:System.Windows.Forms.VisualStyles.VisualStyleElement> definida por el estilo visual actual del sistema operativo. En la información que se puede recuperar de un elemento se incluye su tamaño predeterminado, el tipo de fondo y las definiciones de color.<xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> ajusta la funcionalidad de la API de estilos visuales \(UxTheme\) desde la parte del Shell de Windows de Windows Platform SDK. Para obtener más información, consulte "Using Windows XP Visual Styles" \(Usar estilos visuales de Windows XP\) en la zona de Platform SDK de MSDN Library \(en [http:\/\/msdn.microsoft.com\/library](http://msdn.microsoft.com/library/)\).  
  
 Para obtener más información sobre el uso de <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> y <xref:System.Windows.Forms.VisualStyles.VisualStyleElement>, consulte [Cómo: Representar un elemento de estilo visual](../../../../docs/framework/winforms/controls/how-to-render-a-visual-style-element.md).  
  
## Habilitar los estilos visuales  
 Para habilitar los estilos visuales de una aplicación escrita para la versión 1.0 de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], los programadores deben incluir un manifiesto de aplicación que especifique que se usará la versión 6 o posterior de ComCtl32.dll para dibujar los controles. Para las aplicaciones compiladas con la versión 1.1 o posterior de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], se puede usar el método <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=fullName> de la clase <xref:System.Windows.Forms.Application>.  
  
## Comprobar la compatibilidad de los estilos visuales  
 La propiedad <xref:System.Windows.Forms.Application.RenderWithVisualStyles%2A> de la clase <xref:System.Windows.Forms.Application> indica si la aplicación actual dibuja los controles con estilos visuales. Al pintar un control personalizado, puede comprobar el valor de <xref:System.Windows.Forms.Application.RenderWithVisualStyles%2A> para determinar si debe representar el control con o sin estilos visuales. En la siguiente tabla se muestran las cuatro condiciones que deben cumplirse para que <xref:System.Windows.Forms.Application.RenderWithVisualStyles%2A> devuelva `true`.  
  
|Condición|Notas|  
|---------------|-----------|  
|El sistema operativo es compatible con los estilos visuales.|Para comprobar esta condición por separado, use la propiedad <xref:System.Windows.Forms.VisualStyles.VisualStyleInformation.IsSupportedByOS%2A> de la clase <xref:System.Windows.Forms.VisualStyles.VisualStyleInformation>.|  
|El usuario ha habilitado los estilos visuales en el sistema operativo.|Para comprobar esta condición por separado, use la propiedad <xref:System.Windows.Forms.VisualStyles.VisualStyleInformation.IsEnabledByUser%2A> de la clase <xref:System.Windows.Forms.VisualStyles.VisualStyleInformation>.|  
|Los estilos visuales están habilitados en la aplicación.|Los estilos visuales se pueden habilitar en una aplicación mediante una llamada al método <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=fullName> o usando una aplicación de manifiesto que especifique que se usará la versión 6 o posterior de ComCtl32.dll para dibujar los controles.|  
|Los estilos visuales se usan para dibujar el área de cliente de las ventanas de la aplicación.|Para comprobar esta condición por separado, use la propiedad <xref:System.Windows.Forms.Application.VisualStyleState%2A> de la clase <xref:System.Windows.Forms.Application> y compruebe que tiene el valor <xref:System.Windows.Forms.VisualStyles.VisualStyleState?displayProperty=fullName> o <xref:System.Windows.Forms.VisualStyles.VisualStyleState?displayProperty=fullName>.|  
  
 Para determinar el momento en que un usuario habilita o deshabilita los estilos visuales o cambia de un estilo visual a otro, compruebe el valor <xref:Microsoft.Win32.UserPreferenceCategory?displayProperty=fullName> de los controladores de los eventos <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanging?displayProperty=fullName> o <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged?displayProperty=fullName>.  
  
> [!IMPORTANT]
>  Si quiere usar <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> para representar un control o un elemento de IU cuando el usuario habilita los estilos visuales o cambia de un estilo a otro, asegúrese de llevar a cabo esta acción cuando controle el evento <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanged>, no el evento <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanging>. Si usa la clase <xref:System.Windows.Forms.VisualStyles.VisualStyleRenderer> al controlar <xref:Microsoft.Win32.SystemEvents.UserPreferenceChanging>, se producirá una excepción.  
  
## Vea también  
 [Dibujo y representación personalizados de controles](../../../../docs/framework/winforms/controls/custom-control-painting-and-rendering.md)