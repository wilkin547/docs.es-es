---
title: "Informaci&#243;n general del componente ErrorProvider (Formularios Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ErrorProvider"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "mensajes de error, mostrar"
  - "ErrorProvider (componente) [Windows Forms], acerca del componente ErrorProvider"
  - "errores [Windows Forms], mostrar a usuarios"
ms.assetid: ced189f2-b5c8-46a7-a6f1-37f5af95dc99
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# Informaci&#243;n general del componente ErrorProvider (Formularios Windows Forms)
El componente [ErrorProvider](../../../../docs/framework/winforms/controls/errorprovider-component-windows-forms.md) de formularios Windows Forms se utiliza para validar los datos proporcionados por el usuario en un formulario o en un control.  Habitualmente, se utiliza junto con la validación de entrada del usuario en un formulario o con la presentación de errores dentro de un conjunto de datos.  Un proveedor de errores es una alternativa mejor que mostrar un mensaje de error en un cuadro de mensaje, porque una vez que se descarta un cuadro de mensaje, el mensaje de error deja de estar visible.  El componente <xref:System.Windows.Forms.ErrorProvider> muestra un icono de error \(![Icono ErrorProvider](../../../../docs/framework/winforms/controls/media/vberrorprovidericon.png "vbErrorProviderIcon")\) junto al control correspondiente, por ejemplo, un cuadro de texto; cuando el usuario coloca el puntero del mouse sobre el icono de error, aparece una información sobre herramientas que muestra la cadena del mensaje de error.  
  
## Propiedades principales  
 Las propiedades principales del componente <xref:System.Windows.Forms.ErrorProvider> son <xref:System.Windows.Forms.ErrorProvider.DataSource%2A>, <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> y <xref:System.Windows.Forms.ErrorProvider.Icon%2A>.  Cuando se utiliza el componente <xref:System.Windows.Forms.ErrorProvider> con controles enlazados a datos, la propiedad <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> debe establecerse en el contenedor adecuado \(habitualmente el Windows Form\), para que el componente muestre un icono de error en el formulario.  Cuando se agrega el componente en el diseñador, la propiedad <xref:System.Windows.Forms.ErrorProvider.ContainerControl%2A> se establece en el formulario contenedor; si el usuario agrega el control mediante código, él debe establecerla.  
  
 La propiedad <xref:System.Windows.Forms.ErrorProvider.Icon%2A> puede establecerse en un icono de error personalizado, en lugar del predeterminado.  Cuando la propiedad <xref:System.Windows.Forms.ErrorProvider.DataSource%2A> está establecida, el componente <xref:System.Windows.Forms.ErrorProvider> puede mostrar mensajes de error para un conjunto de datos.  El método clave del componente <xref:System.Windows.Forms.ErrorProvider> es el método <xref:System.Windows.Forms.ErrorProvider.SetError%2A>, que especifica la cadena del mensaje de error y dónde debe aparecer el icono de error.  
  
> [!NOTE]
>  El componente <xref:System.Windows.Forms.ErrorProvider> no proporciona compatibilidad integrada para los clientes de accesibilidad.  Para que la aplicación sea accesible al utilizar este componente, debe proporcionar un mecanismo de respuesta adicional que sea accesible.  
  
## Vea también  
 <xref:System.Windows.Forms.ErrorProvider>   
 [Cómo: Ver errores de un conjunto de datos con el componente ErrorProvider de formularios Windows Forms](../../../../docs/framework/winforms/controls/view-errors-within-a-dataset-with-wf-errorprovider-component.md)   
 [Cómo: Mostrar iconos de error para la validación de formularios con el componente ErrorProvider de formularios Windows Forms](../../../../docs/framework/winforms/controls/display-error-icons-for-form-validation-with-wf-errorprovider.md)