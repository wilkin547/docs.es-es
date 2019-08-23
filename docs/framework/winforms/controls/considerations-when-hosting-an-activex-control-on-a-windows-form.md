---
title: Consideraciones al alojar un control ActiveX en Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- ActiveX controls [Windows Forms], hosting
- Windows Forms, ActiveX controls
- Windows Forms, hosting ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 2509302d-a74e-484f-9890-2acdbfa67a68
ms.openlocfilehash: 0b95bab20299b966b9f3c6e6ce089a641670f974
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933410"
---
# <a name="considerations-when-hosting-an-activex-control-on-a-windows-form"></a>Consideraciones al alojar un control ActiveX en Windows Forms
Aunque Windows Forms se han optimizado para hospedar controles de Windows Forms, todavía puede utilizar los controles ActiveX. Tenga en cuenta las consideraciones siguientes al planear una aplicación que utiliza controles ActiveX:  
  
- **Seguridad** Se ha mejorado Common Language Runtime con respecto a la seguridad de acceso del código. Las aplicaciones que incluyen Windows Forms pueden ejecutarse en un entorno de plena confianza sin problema y en un entorno de confianza parcial con la mayoría de la funcionalidad accesible. Los controles de Windows Forms se pueden hospedar en un explorador sin ninguna complicación. Sin embargo, los controles ActiveX en Windows Forms no pueden aprovechar estas mejoras de seguridad. La ejecución de un control ActiveX requiere el permiso del código no administrado, que se <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A?displayProperty=nameWithType> establece con la propiedad. Para obtener más información acerca de la seguridad y el permiso de código <xref:System.Security.Permissions.SecurityPermissionAttribute>no administrado, vea.  
  
- **Costo total de propiedad** Los controles ActiveX agregados a Windows Forms se implementan con ese formulario Windows Forms en su totalidad, lo que puede aumentar significativamente el tamaño de los archivos creados. Además, el uso de los controles ActiveX en Windows Forms requiere que se escriba en el registro. Esto es más invasor para un equipo de usuario que los controles de Windows Forms, que no lo necesitan.  
  
    > [!NOTE]
    > Trabajar con un control ActiveX requiere el uso de un contenedor de interoperabilidad COM. Para más información, consulte [Interoperabilidad COM en Visual Basic y Visual C#](../../../visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
    > [!NOTE]
    > Si el nombre de un miembro del control ActiveX coincide con un nombre definido en el .NET Framework, el importador de controles ActiveX agregará el prefijo **CTL** al nombre del miembro al crear <xref:System.Windows.Forms.AxHost> la clase derivada. Por ejemplo, si el control ActiveX tiene un miembro denominado **layout**, se le cambia el nombre de **CtlLayout** en la clase derivada de AxHost porque el evento de **diseño** está definido en el .NET Framework.  
  
## <a name="see-also"></a>Vea también

- [Cómo: Agregar controles ActiveX a Windows Forms](how-to-add-activex-controls-to-windows-forms.md)
- [Seguridad de acceso del código](../../misc/code-access-security.md)
- [Comparación de los controles y objetos programables de distintos lenguajes y bibliotecas](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))
- [Insertar controles en Windows Forms](putting-controls-on-windows-forms.md)
- [Controles de formularios Windows Forms](index.md)
