---
title: "C&#243;mo: Compartir datos enlazados entre formularios mediante el componente BindingSource | Microsoft Docs"
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
  - "BindingSource (componente) [Windows Forms], ejemplos"
  - "BindingSource., usar con varios formularios"
  - "enlace de datos, compartir datos entre formularios"
  - "ejemplos [Windows Forms], BindingSource (componente)"
ms.assetid: a1a49630-db9c-4485-b888-1f62a373a4f7
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Compartir datos enlazados entre formularios mediante el componente BindingSource
Puede compartir datos fácilmente entre formularios con el componente <xref:System.Windows.Forms.BindingSource>.  Por ejemplo, quizás quiera mostrar un formulario de solo lectura que resume los datos del origen de datos y otro formulario editable que contiene información detallada sobre el elemento seleccionado actualmente en el origen de datos.  Este ejemplo muestra este escenario.  
  
## Ejemplo  
 En el ejemplo de código siguiente se muestra cómo compartir un <xref:System.Windows.Forms.BindingSource> y sus datos enlazados entre formularios.  En este ejemplo, el <xref:System.Windows.Forms.BindingSource> compartido se pasa al constructor del formulario secundario.  El formulario secundario permite al usuario editar los datos del elemento actualmente seleccionado en el formulario principal.  
  
> [!NOTE]
>  El evento <xref:System.Windows.Forms.BindingSource.BindingComplete> del componente <xref:System.Windows.Forms.BindingSource> se controla en el ejemplo para asegurarse de que los dos formularios permanecen sincronizadas.  Para obtener más información acerca de por qué se hace así, consulte [Cómo: Garantizar que varios controles enlazados al mismo origen de datos permanezcan sincronizados](../../../../docs/framework/winforms/multiple-controls-bound-to-data-source-synchronized.md).  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleForms#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleForms#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/VB/Form1.vb#1)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados System, System.Windows.Forms, System.Drawing, System.Data y System.Xml.  
  
 Para obtener información acerca de cómo compilar este ejemplo desde la línea de comandos para [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], consulte [Compilar desde la línea de comandos](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) o [Compilar la línea de comandos con csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  También puede compilar este ejemplo en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] pegando el código en un nuevo proyecto.  Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228%20\(v=vs.110\)).  
  
## Vea también  
 [BindingSource \(Componente\)](../../../../docs/framework/winforms/controls/bindingsource-component.md)   
 [Enlace de datos en Windows Forms](../../../../docs/framework/winforms/windows-forms-data-binding.md)   
 [Cómo: Controlar errores y excepciones que se producen con el enlace de datos](../../../../docs/framework/winforms/controls/how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)