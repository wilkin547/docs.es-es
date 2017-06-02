---
title: "C&#243;mo: Admitir la interoperabilidad COM al mostrar Windows Forms en sus propios subprocesos | Microsoft Docs"
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
  - "Interoperabilidad COM, Windows Forms"
  - "COM [Windows Forms]"
  - "Windows Forms, sin administrar"
  - "Controles ActiveX [Windows Forms], interoperabilidad COM"
  - "Windows Forms, interoperabilidad"
ms.assetid: a9e04765-d2de-4389-a494-a9a6d07aa6ee
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Admitir la interoperabilidad COM al mostrar Windows Forms en sus propios subprocesos
Puede resolver problemas de interoperabilidad COM mostrando el formulario en un bucle de mensajes de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], que puede crear con el método <xref:System.Windows.Forms.Application.Run%2A?displayProperty=fullName>.  
  
 Para que un Windows Form funcione correctamente con una aplicación cliente COM, debe ejecutar el formulario en un bucle de mensajes de Windows Forms. Para ello, siga uno de estos procedimientos:  
  
-   Use el método <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=fullName> para mostrar el Windows Form. Para obtener más información, consulta [Cómo: Admitir la interoperabilidad COM al mostrar Windows Forms con el método ShowDialog](../../../../docs/framework/winforms/advanced/com-interop-by-displaying-a-windows-form-shadow.md).  
  
-   Muestre cada Windows Form en un subproceso independiente.  
  
 Hay una amplia compatibilidad para esta característica en [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].  
  
 Consulte también [Tutorial: Admitir la interoperabilidad COM al mostrar Windows Forms en su propio subproceso](http://msdn.microsoft.com/library/ms233639\(v=vs.110\)).  
  
## Ejemplo  
 En el ejemplo de código siguiente se ilustra cómo mostrar el formulario en un subproceso independiente y cómo llamar al método <xref:System.Windows.Forms.Application.Run%2A?displayProperty=fullName> para iniciar un bombeo de mensajes de Windows Forms en ese subproceso. Para usar este enfoque, debe calcular las referencias de las llamadas al formulario desde la aplicación no administrada usando el método <xref:System.Windows.Forms.Control.Invoke%2A>.  
  
 Este enfoque requiere que cada instancia de un formulario se ejecuta en su propio subproceso usando su propio bucle de mensajes. No puede tener más de un bucle de mensajes en ejecución por subproceso. Por lo tanto, no puede cambiar el bucle de mensajes de la aplicación cliente. Sin embargo, puede modificar el componente [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] para iniciar un nuevo subproceso que use su propio bucle de mensajes.  
  
 [!code-vb[System.Windows.Forms.ComInterop#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ComInterop/VB/COMForm.vb#1)]  
  
 [!code-vb[System.Windows.Forms.ComInterop#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ComInterop/VB/FormManager.vb#10)]  
  
 [!code-vb[System.Windows.Forms.ComInterop#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ComInterop/VB/Form1.vb#100)]  
  
## Compilar el código  
  
-   Compile los tipos `COMForm`, `Form1` y `FormManager` en un ensamblado llamado `COMWinform.dll`. Registre el ensamblado para la interoperabilidad COM usando uno de los métodos descritos en [Packaging an Assembly for COM](../../../../docs/framework/interop/packaging-an-assembly-for-com.md). Ahora puede usar el ensamblado y el archivo de biblioteca de tipos \(.tlb\) correspondiente en las aplicaciones no administradas. Por ejemplo, puede usar la biblioteca de tipos como una referencia en un proyecto ejecutable de Visual Basic 6.0.  
  
## Vea también  
 [Exposing .NET Framework Components to COM](../../../../docs/framework/interop/exposing-dotnet-components-to-com.md)   
 [Packaging an Assembly for COM](../../../../docs/framework/interop/packaging-an-assembly-for-com.md)   
 [Registering Assemblies with COM](../../../../docs/framework/interop/registering-assemblies-with-com.md)   
 [Cómo: Admitir la interoperabilidad COM al mostrar Windows Forms con el método ShowDialog](../../../../docs/framework/winforms/advanced/com-interop-by-displaying-a-windows-form-shadow.md)   
 [Información general sobre formularios Windows Forms y aplicaciones no administradas](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications-overview.md)