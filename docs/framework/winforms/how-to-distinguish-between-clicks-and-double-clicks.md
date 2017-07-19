---
title: "How to: Distinguish Between Clicks and Double-Clicks | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "mouse, click"
  - "mouse, double-click"
  - "mouse clicks, single versus double"
ms.assetid: d836ac8c-85bc-4f3a-a761-8aee03dc682c
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# How to: Distinguish Between Clicks and Double-Clicks
Normalmente, un único *clic* inicia una acción de la interfaz de usuario \(UI\) y un *doble clic* extiende la acción.  Por ejemplo, un clic normalmente selecciona un elemento y un doble clic edita el elemento seleccionado.  Sin embargo, los eventos de clic de Windows Forms no se adaptan fácilmente un escenario en el que un clic y un doble clic realizan acciones incompatibles, ya que una acción asociada al evento <xref:System.Windows.Forms.Control.Click> o <xref:System.Windows.Forms.Control.MouseClick> se realiza antes de la acción asociada al evento <xref:System.Windows.Forms.Control.DoubleClick> o <xref:System.Windows.Forms.Control.MouseDoubleClick>.  Este tema se muestran dos soluciones a este problema.  Una solución es controlar el evento de doble clic y revertir las acciones en el control del evento de clic.  En raras ocasiones, puede que necesite simular el comportamiento de clic y doble clic controlando el evento <xref:System.Windows.Forms.Control.MouseDown> y usando las propiedades <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> y <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A> de la clase <xref:System.Windows.Forms.SystemInformation>.  Mida el tiempo entre los clics y si se produce un segundo clic antes de alcanzar el valor de <xref:System.Windows.Forms.SystemInformation.DoubleClickTime%2A> y el clic en está dentro de un rectángulo definido por <xref:System.Windows.Forms.SystemInformation.DoubleClickSize%2A>, realice la acción de doble clic; de lo contrario, realice la acción de clic.  
  
### Para revertir una acción de clic  
  
-   Asegúrese de que el control con el que trabaja tiene un comportamiento de doble clic estándar.  Si no es así, habilite el control con el método <xref:System.Windows.Forms.Control.SetStyle%2A>.  Controle el evento de doble clic y revierta la acción de clic, así como la acción de doble clic.  En el ejemplo de código siguiente se muestra cómo crear un botón personalizado con el doble clic habilitado, y cómo revertir la acción de clic en el código de control de eventos de doble clic.  
  
     [!code-csharp[System.Windows.Forms.ButtonDoubleClick#1](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ButtonDoubleClick/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ButtonDoubleClick#1](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ButtonDoubleClick/VB/Form1.vb#1)]  
  
### Para distinguir entre los clics en el evento MouseDown  
  
-   Controle el evento <xref:System.Windows.Forms.Control.MouseDown> y determine la ubicación y el intervalo de tiempo entre los clics usando las propiedades <xref:System.Windows.Forms.SystemInformation> adecuadas y un componente <xref:System.Windows.Forms.Timer>.  Realice las acciones apropiadas en función de si tiene lugar un clic o un doble clic.  En el ejemplo de código siguiente se muestra cómo hacer esto.  
  
     [!code-cpp[System.Windows.Forms.SingleVersusDoubleClick#0](../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SingleVersusDoubleClick/cpp/form1.cpp#0)]
     [!code-csharp[System.Windows.Forms.SingleVersusDoubleClick#0](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SingleVersusDoubleClick/CS/form1.cs#0)]
     [!code-vb[System.Windows.Forms.SingleVersusDoubleClick#0](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SingleVersusDoubleClick/VB/form1.vb#0)]  
  
## Compilar el código  
 Para estos ejemplos se necesita:  
  
-   Referencias a los ensamblados System, System.Drawing y System.Windows.Forms.  
  
 Para obtener información acerca de cómo compilar estos ejemplos desde la línea de comandos para [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] o [!INCLUDE[csprcs](../../../includes/csprcs-md.md)], consulte [Compilar desde la línea de comandos](../Topic/Building%20from%20the%20Command%20Line%20\(Visual%20Basic\).md) o [Compilar la línea de comandos con csc.exe](../../../ocs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  También puede compilar estos ejemplos en [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] pegando el código en proyectos nuevos.  Consulte también [Cómo: Compilar y ejecutar un ejemplo de código completo de Windows Forms en Visual Studio](http://msdn.microsoft.com/library/Bb129228%20\(v=vs.110\)).  
  
## Vea también  
 [Mouse Input in a Windows Forms Application](../../../docs/framework/winforms/mouse-input-in-a-windows-forms-application.md)