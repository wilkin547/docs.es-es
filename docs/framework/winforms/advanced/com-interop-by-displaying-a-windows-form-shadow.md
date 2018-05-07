---
title: 'Cómo: Admitir la interoperabilidad COM al mostrar Windows Forms con el método ShowDialog'
ms.date: 03/30/2017
helpviewer_keywords:
- COM [Windows Forms]
- Windows Forms, unmanaged
- COM interop [Windows Forms], calling methods
- ActiveX controls [Windows Forms], COM interop
- Windows Forms, interop
ms.assetid: 87aac8ad-3c04-43b3-9b0c-d0b00df9ee74
ms.openlocfilehash: c764395b7926a131deae4109fed3a7461c45e2d1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-support-com-interop-by-displaying-a-windows-form-with-the-showdialog-method"></a>Cómo: Admitir la interoperabilidad COM al mostrar Windows Forms con el método ShowDialog
Puede resolver problemas de interoperabilidad del Modelo de objetos componentes (COM) mostrando el formulario de Windows Forms en un bucle de mensajes de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], que se crea con el método <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType>.  
  
 Para que un formulario funcione correctamente con una aplicación cliente COM, debe ejecutarlo en un bucle de mensajes de Windows Forms. Para ello, siga uno de estos procedimientos:  
  
-   Use el método <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> para mostrar el formulario de Windows Forms.  
  
-   Muestre cada Windows Form en un subproceso independiente. Para obtener más información, consulta [How to: Support COM Interop by Displaying Each Windows Form on Its Own Thread](../../../../docs/framework/winforms/advanced/how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md).  
  
## <a name="procedure"></a>Procedimiento  
 El uso del método <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> puede ser la manera más fácil de mostrar un formulario en un bucle de mensajes de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] porque, de todos los enfoques, es el que necesita menos código para su implementación.  
  
 El método <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> suspende el bucle de mensajes de la aplicación no administrada y muestra el formulario en forma de cuadro de diálogo. Una vez suspendido el bucle de mensajes de la aplicación host, el método <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> crea otro bucle de mensajes de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] para procesar los mensajes del formulario.  
  
 La desventaja a la hora de usar el método <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> es que el formulario se abrirá como un cuadro de diálogo modal. Este comportamiento bloquea cualquier interfaz de usuario (IU) de la aplicación que hace la llamada mientras el formulario de Windows Forms esté abierto. Cuando el usuario sale del formulario, el bucle de mensajes de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] se cierra y el bucle de mensajes de la primera aplicación vuelve a ejecutarse.  
  
 Puede crear una biblioteca de clases en Windows Forms que tenga un método para mostrar el formulario y, después, compilar la biblioteca de clases para la interoperabilidad COM. Puede usar este archivo DLL desde Visual Basic 6.0 o desde Microsoft Foundation Classes (MFC); además, desde cualquiera de estos entornos puede llamar al método <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> para mostrar el formulario.  
  
#### <a name="to-support-com-interop-by-displaying-a-windows-form-with-the-showdialog-method"></a>Para admitir la interoperabilidad COM mostrando un formulario de Windows Forms con el método ShowDialog  
  
-   Reemplace todas las llamadas al método <xref:System.Windows.Forms.Form.Show%2A?displayProperty=nameWithType> por llamadas al método <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> en su componente de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)].  
  
## <a name="see-also"></a>Vea también  
 [Exponer componentes de .NET Framework en COM](../../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 [Cómo: Admitir la interoperabilidad COM al mostrar Windows Forms en sus propios subprocesos](../../../../docs/framework/winforms/advanced/how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)  
 [Aplicaciones de Windows Forms y aplicaciones no administradas](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications.md)
