---
title: 'Cómo: Admitir la interoperabilidad COM al mostrar Windows Forms en sus propios subprocesos'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- vb
helpviewer_keywords:
- COM interop [Windows Forms], Windows Forms
- COM [Windows Forms]
- Windows Forms, unmanaged
- ActiveX controls [Windows Forms], COM interop
- Windows Forms, interop
ms.assetid: a9e04765-d2de-4389-a494-a9a6d07aa6ee
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f5d8a0351fc206aad9d88f9ca3f7c930ff853ff7
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread"></a>Cómo: Admitir la interoperabilidad COM al mostrar Windows Forms en sus propios subprocesos
Puede resolver problemas de interoperabilidad COM mostrando el formulario en un bucle de mensajes de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], que puede crear con el método <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType>.  
  
 Para que un Windows Form funcione correctamente con una aplicación cliente COM, debe ejecutar el formulario en un bucle de mensajes de Windows Forms. Para ello, siga uno de estos procedimientos:  
  
-   Use el método <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> para mostrar el Windows Form. Para obtener más información, consulta [How to: Support COM Interop by Displaying a Windows Form with the ShowDialog Method](../../../../docs/framework/winforms/advanced/com-interop-by-displaying-a-windows-form-shadow.md).  
  
-   Muestre cada Windows Form en un subproceso independiente.  
  
 Hay una amplia compatibilidad para esta característica en Visual Studio.  
  
 Consulte también [Tutorial: Admitir la interoperabilidad COM al mostrar Windows Forms en su propio subproceso](http://msdn.microsoft.com/library/ms233639\(v=vs.110\)).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo de código siguiente se ilustra cómo mostrar el formulario en un subproceso independiente y cómo llamar al método <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> para iniciar un bombeo de mensajes de Windows Forms en ese subproceso. Para usar este enfoque, debe calcular las referencias de las llamadas al formulario desde la aplicación no administrada usando el método <xref:System.Windows.Forms.Control.Invoke%2A> .  
  
 Este enfoque requiere que cada instancia de un formulario se ejecuta en su propio subproceso usando su propio bucle de mensajes. No puede tener más de un bucle de mensajes en ejecución por subproceso. Por lo tanto, no puede cambiar el bucle de mensajes de la aplicación cliente. Sin embargo, puede modificar el componente [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] para iniciar un nuevo subproceso que use su propio bucle de mensajes.  
  
 [!code-vb[System.Windows.Forms.ComInterop#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ComInterop/VB/COMForm.vb#1)]  
  
 [!code-vb[System.Windows.Forms.ComInterop#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ComInterop/VB/FormManager.vb#10)]  
  
 [!code-vb[System.Windows.Forms.ComInterop#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ComInterop/VB/Form1.vb#100)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
  
-   Compile los tipos `COMForm`, `Form1`y `FormManager` en un ensamblado llamado `COMWinform.dll`. Registre el ensamblado para la interoperabilidad COM usando uno de los métodos descritos en [Packaging an Assembly for COM](../../../../docs/framework/interop/packaging-an-assembly-for-com.md). Ahora puede usar el ensamblado y el archivo de biblioteca de tipos (.tlb) correspondiente en las aplicaciones no administradas. Por ejemplo, puede usar la biblioteca de tipos como una referencia en un proyecto ejecutable de Visual Basic 6.0.  
  
## <a name="see-also"></a>Vea también  
 [Exponer componentes de .NET Framework en COM](../../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 [Empaquetar un ensamblado para COM](../../../../docs/framework/interop/packaging-an-assembly-for-com.md)  
 [Registrar ensamblados con COM](../../../../docs/framework/interop/registering-assemblies-with-com.md)  
 [Admitir la interoperabilidad COM al mostrar Windows Forms con el método ShowDialog](../../../../docs/framework/winforms/advanced/com-interop-by-displaying-a-windows-form-shadow.md)  
 [Información general sobre formularios Windows Forms y aplicaciones no administradas](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications-overview.md)
