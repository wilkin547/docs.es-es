---
title: "C&#243;mo: Agregar funciones de explorador Web a una aplicaci&#243;n de Windows Forms | Microsoft Docs"
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
  - "ejemplos [Windows Forms], WebBrowser (control)"
  - "exploradores Web [.NET Framework], agregar a Windows Forms"
  - "WebBrowser (control) [Windows Forms], agregar funciones del explorador Web a la aplicación"
  - "WebBrowser (control) [Windows Forms], ejemplos"
  - "Windows Forms, agregar funcionalidades del explorador Web"
ms.assetid: 3871f072-b57a-435b-9976-e5da28df04a7
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# C&#243;mo: Agregar funciones de explorador Web a una aplicaci&#243;n de Windows Forms
Con el control <xref:System.Windows.Forms.WebBrowser>, puede agregar funcionalidades del explorador web a la aplicación.  De forma predeterminada, el control funciona como un explorador web.  Después de cargar una dirección URL inicial estableciendo la propiedad <xref:System.Windows.Forms.WebBrowser.Url%2A>, puede navegar haciendo clic en hipervínculos o utilizando métodos abreviados de teclado para avanzar y retroceder por el historial de navegación.  De forma predeterminada, puede acceder a funcionalidades adicionales del explorador a través del menú contextual.  También puede abrir documentos nuevos colocándolos en el control.  El control <xref:System.Windows.Forms.WebBrowser> también tiene varias propiedades, métodos y eventos que puede utilizar para implementar características de interfaz de usuario similares a las que se encuentran en Internet Explorer.  
  
 En el ejemplo de código siguiente, se implementa una barra de direcciones, los botones de exploración típicos, un menú **Archivo**, una barra de estado y una barra de título que muestra el título de la página actual.  
  
## Ejemplo  
 [!code-cpp[System.Windows.Forms.WebBrowser#0](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/CPP/form1.cpp#0)]
 [!code-csharp[System.Windows.Forms.WebBrowser#0](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.WebBrowser#0](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.WebBrowser/VB/form1.vb#0)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los ensamblados `System,` `System.Drawing` y `System.Windows.Forms`.  
  
 Para obtener información acerca de cómo generar este ejemplo desde la línea de comandos para [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], consulte [Compilar desde la línea de comandos](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) o [Compilar la línea de comandos con csc.exe](../../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  También puede compilar este ejemplo en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] pegando el código en un nuevo proyecto.  Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).  
  
## Vea también  
 <xref:System.Windows.Forms.WebBrowser>   
 [WebBrowser \(Control\)](../../../../docs/framework/winforms/controls/webbrowser-control-windows-forms.md)