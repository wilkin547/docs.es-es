---
title: "C&#243;mo: Crear cuadr&#237;culas de propiedades para la configuraci&#243;n del usuario en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Settings (objeto), crear cuadrículas de propiedades para la configuración del usuario"
  - "cuadrículas de propiedades"
  - "cuadrículas de propiedades, crear para la configuración del usuario"
  - "configuración del usuario, crear cuadrículas de propiedades"
ms.assetid: b0bc737e-50d1-43d1-a6df-268db6e6f91c
caps.latest.revision: 13
caps.handback.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Crear cuadr&#237;culas de propiedades para la configuraci&#243;n del usuario en Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

Puede crear una cuadrícula de propiedades para la configuración del usuario rellenando un control <xref:System.Windows.Forms.PropertyGrid> con las propiedades de configuración de usuario del objeto `My.Settings`.  
  
> [!NOTE]
>  Para que este ejemplo funcione, su aplicación debe tener definida la configuración del usuario.  Para obtener más información, vea [Administrar la configuración de la aplicación \(.NET\)](/visual-studio/ide/managing-application-settings-dotnet).  
  
 El objeto `My.Settings` expone cada configuración como una propiedad.  El nombre de propiedad es igual que el nombre de la configuración y el tipo de propiedad es igual que el tipo de configuración.  El **Ámbito** de la configuración determina si la propiedad es de sólo lectura; la propiedad de una configuración de ámbito **Aplicación** es de sólo lectura, en tanto que la propiedad de una configuración de ámbito **Usuario** es de lectura y escritura.  Para obtener más información, vea [My.Settings \(Objeto\)](../../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
> [!NOTE]
>  No puede cambiar ni guardar en tiempo de ejecución los valores de configuración de ámbito de aplicación.  La configuración de ámbito de aplicación sólo se puede cambiar al crear la aplicación \(mediante el **Diseñador de proyectos**\) o editando el archivo de configuración de la aplicación.  Para obtener más información, vea [Administrar la configuración de la aplicación \(.NET\)](/visual-studio/ide/managing-application-settings-dotnet).  
  
 Este ejemplo utiliza un control <xref:System.Windows.Forms.PropertyGrid> para tener acceso a las propiedades de configuración del usuario del objeto `My.Settings`.  De manera predeterminada, <xref:System.Windows.Forms.PropertyGrid> muestra todas las propiedades del objeto `My.Settings`.  Sin embargo, las propiedades de configuración del usuario tienen el atributo <xref:System.Configuration.UserScopedSettingAttribute>.  Este ejemplo establece la propiedad <xref:System.Windows.Forms.PropertyGrid.BrowsableAttributes%2A> de <xref:System.Windows.Forms.PropertyGrid> en <xref:System.Configuration.UserScopedSettingAttribute> para mostrar sólo las propiedades de configuración del usuario.  
  
### Para agregar una cuadrícula de propiedades de configuración de usuario  
  
1.  Agregue el control **PropertyGrid** del **Cuadro de herramientas** a la superficie de diseño de la aplicación, que aquí será  `Form1`.  
  
     El nombre predeterminado del control de cuadrícula de propiedades es `PropertyGrid1`.  
  
2.  Haga doble clic en la superficie de diseño de `Form1` para abrir el código del controlador de eventos de carga del formulario.  
  
3.  Establezca el objeto `My.Settings` como el objeto seleccionado para la cuadrícula de propiedades.  
  
     [!code-vb[VbVbalrMyResources#11](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-create-property-grids-for-user-settings_1.vb)]  
  
4.  Configure la cuadrícula de propiedades para mostrar sólo la configuración del usuario.  
  
     [!code-vb[VbVbalrMyResources#12](../../../../visual-basic/developing-apps/programming/app-settings/codesnippet/VisualBasic/how-to-create-property-grids-for-user-settings_2.vb)]  
  
    > [!NOTE]
    >  Para mostrar sólo la configuración de ámbito de aplicación, utilice el atributo <xref:System.Configuration.ApplicationScopedSettingAttribute> en lugar <xref:System.Configuration.UserScopedSettingAttribute>.  
  
## Programación eficaz  
 La aplicación guarda la configuración del usuario cuando se cierra.  Para guardar inmediatamente la configuración, llame al método `My.Settings.Save`.  Para obtener más información, vea [Cómo: Conservar la configuración del usuario en Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md).  
  
## Vea también  
 [My.Settings \(Objeto\)](../../../../visual-basic/language-reference/objects/my-settings-object.md)   
 [Cómo: Leer la configuración de la aplicación en Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)   
 [Cómo: Cambiar la configuración del usuario en Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-change-user-settings.md)   
 [Cómo: Conservar la configuración del usuario en Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)   
 [Administrar la configuración de la aplicación \(.NET\)](/visual-studio/ide/managing-application-settings-dotnet)