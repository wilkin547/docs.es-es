---
title: Procedimiento para admitir la interoperabilidad COM mostrando un formulario Windows Forms con el método ShowDialog
ms.date: 03/30/2017
helpviewer_keywords:
- COM [Windows Forms]
- Windows Forms, unmanaged
- COM interop [Windows Forms], calling methods
- ActiveX controls [Windows Forms], COM interop
- Windows Forms, interop
ms.assetid: 87aac8ad-3c04-43b3-9b0c-d0b00df9ee74
ms.openlocfilehash: f2fb48e07243694b14904b240bdcb0739175c2fc
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65593530"
---
# <a name="how-to-support-com-interop-by-displaying-a-windows-form-with-the-showdialog-method"></a>Procedimiento para admitir la interoperabilidad COM mostrando un formulario Windows Forms con el método ShowDialog
Puede resolver problemas de interoperabilidad del modelo de objetos componentes (COM) mostrando el formulario de Windows en un bucle de mensajes de .NET Framework, que se crea mediante el <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> método.  
  
 Para que un formulario funcione correctamente con una aplicación cliente COM, debe ejecutarlo en un bucle de mensajes de Windows Forms. Para ello, siga uno de estos procedimientos:  
  
- Use el método <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> para mostrar el formulario de Windows Forms.  
  
- Muestre cada Windows Form en un subproceso independiente. Para obtener más información, vea [Cómo: Admitir la interoperabilidad COM al mostrar Windows Forms en su propio subproceso](how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md).  
  
## <a name="procedure"></a>Procedimiento  
 Mediante el <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> método puede ser la manera más fácil de mostrar un formulario en un bucle de mensajes de .NET Framework porque, de todos los enfoques, requiere menos código para implementar.  
  
 El método <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> suspende el bucle de mensajes de la aplicación no administrada y muestra el formulario en forma de cuadro de diálogo. Ya se ha suspendido el bucle de mensajes de la aplicación host, el <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> método crea un nuevo bucle de mensajes de .NET Framework para procesar los mensajes del formulario.  
  
 La desventaja a la hora de usar el método <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> es que el formulario se abrirá como un cuadro de diálogo modal. Este comportamiento bloquea cualquier interfaz de usuario (IU) de la aplicación que hace la llamada mientras el formulario de Windows Forms esté abierto. Cuando el usuario sale del formulario, se cierra el bucle de mensajes de .NET Framework y el bucle de mensajes de la aplicación anterior comienza a ejecutarse de nuevo.  
  
 Puede crear una biblioteca de clases en Windows Forms que tenga un método para mostrar el formulario y, después, compilar la biblioteca de clases para la interoperabilidad COM. Puede usar este archivo DLL desde Visual Basic 6.0 o desde Microsoft Foundation Classes (MFC); además, desde cualquiera de estos entornos puede llamar al método <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> para mostrar el formulario.  
  
#### <a name="to-support-com-interop-by-displaying-a-windows-form-with-the-showdialog-method"></a>Para admitir la interoperabilidad COM mostrando un formulario de Windows Forms con el método ShowDialog  
  
- Reemplace todas las llamadas a la <xref:System.Windows.Forms.Form.Show%2A?displayProperty=nameWithType> método con las llamadas a la <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> método en el componente de .NET Framework.  
  
## <a name="see-also"></a>Vea también

- [Exponer componentes de .NET Framework en COM](../../interop/exposing-dotnet-components-to-com.md)
- [Cómo: Admitir la interoperabilidad COM al mostrar Windows Forms en su propio subproceso](how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)
- [Aplicaciones de Windows Forms y aplicaciones no administradas](windows-forms-and-unmanaged-applications.md)
