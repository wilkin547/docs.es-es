---
title: "C&#243;mo: Utilizar las propiedades Modifiers y GenerateMember | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Designer_GenerateMember"
  - "Designer_Modifiers"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "formularios base"
  - "herencia de formularios"
  - "GenerateMember (propiedad)"
  - "herencia, formularios"
  - "formularios heredados"
  - "formularios heredados, Windows Forms"
  - "Modifiers (propiedad)"
  - "Windows Forms, herencia"
ms.assetid: 3381a5e4-e1a3-44e2-a765-a0b758937b85
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Utilizar las propiedades Modifiers y GenerateMember
Cuando coloca un componente en un Windows Form, el entorno de diseño proporciona dos propiedades: `GenerateMember` y `Modifiers`.  La propiedad `GenerateMember` especifica cuándo el Diseñador de Windows Forms genera una variable miembro para un componente.  La propiedad `Modifiers` es el modificador de acceso asignado a esa variable miembro.  Si el valor de la propiedad `GenerateMember` es `false`, el valor de la propiedad `Modifiers` no tiene ningún efecto.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para especificar si un componente es un miembro del formulario  
  
1.  En el Diseñador de Windows Forms, abra el formulario.  
  
2.  Abra el **Cuadro de herramientas** y, en el formulario, coloque tres controles <xref:System.Windows.Forms.Button>.  
  
3.  Establezca las propiedades `GenerateMember` y `Modifiers` para cada control <xref:System.Windows.Forms.Button> según la tabla siguiente.  
  
    |Nombre de botón|Valor de GenerateMember|Valor de Modifiers|  
    |---------------------|-----------------------------|------------------------|  
    |`button1`|`true`|`private`|  
    |`button2`|`true`|`protected`|  
    |`button3`|`false`|Sin cambios|  
  
4.  Compile la solución.  
  
5.  En el **Explorador de soluciones**, haga clic en el botón **Mostrar todos los archivos**.  
  
6.  Abra el nodo **Form1** y, en el **Editor de código**,  abra el archivo **Form1.Designer.vb** o **Form1.Designer.cs**.  Este archivo contiene el código emitido por el Diseñador de Windows Forms.  
  
7.  Encuentre las declaraciones para los tres botones.  En el ejemplo de código siguiente se muestran las diferencias especificadas por las propiedades `GenerateMember` y `Modifiers`.  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.GenerateMember#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#3)]  
  
     [!code-csharp[System.Windows.Forms.GenerateMember#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.GenerateMember#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#2)]  
  
> [!NOTE]
>  De forma predeterminada, el Diseñador de Windows Forms asigna el modificador `private` \(`Friend` en Visual Basic\) a controles contenedores como <xref:System.Windows.Forms.Panel>.  Si el <xref:System.Windows.Forms.UserControl> o <xref:System.Windows.Forms.Form> base tiene un control contenedor, no aceptará nuevos elementos secundarios en controles y formularios heredados.  La solución es cambiar el modificador del control contenedor base a `protected` o `public`.  
  
## Vea también  
 <xref:System.Windows.Forms.Button>   
 [Herencia visual de formularios Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-visual-inheritance.md)   
 [Tutorial: Demostración de la herencia visual](../../../../docs/framework/winforms/advanced/walkthrough-demonstrating-visual-inheritance.md)   
 [Cómo: Heredar formularios Windows Forms](../../../../docs/framework/winforms/advanced/how-to-inherit-windows-forms.md)