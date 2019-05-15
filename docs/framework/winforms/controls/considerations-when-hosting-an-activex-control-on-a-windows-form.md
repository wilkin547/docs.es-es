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
ms.openlocfilehash: 4b604502e0fea591460f30cae28b64ff1703da65
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2019
ms.locfileid: "65589439"
---
# <a name="considerations-when-hosting-an-activex-control-on-a-windows-form"></a>Consideraciones al alojar un control ActiveX en Windows Forms
Aunque Windows Forms se han optimizado para hospedar controles de Windows Forms, todavía puede utilizar los controles ActiveX. Tenga en cuenta las consideraciones siguientes al planear una aplicación que utiliza controles ActiveX:  
  
- **Seguridad** Se ha mejorado Common Language Runtime con respecto a la seguridad de acceso del código. Las aplicaciones que incluyen Windows Forms pueden ejecutarse en un entorno de plena confianza sin problema y en un entorno de confianza parcial con la mayoría de la funcionalidad accesible. Los controles de Windows Forms se pueden hospedar en un explorador sin ninguna complicación. Sin embargo, los controles ActiveX en Windows Forms no pueden aprovechar estas mejoras de seguridad. Ejecución de un control ActiveX requiere permiso de código no administrado, que se establece con el <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A?displayProperty=nameWithType> propiedad. Para obtener más información sobre seguridad y el permiso de código no administrado, consulte <xref:System.Security.Permissions.SecurityPermissionAttribute>.  
  
- **Costo total de propiedad** Los controles ActiveX agregados a Windows Forms se implementan con ese formulario Windows Forms en su totalidad, lo que puede aumentar significativamente el tamaño de los archivos creados. Además, el uso de los controles ActiveX en Windows Forms requiere que se escriba en el registro. Esto es más invasor para un equipo de usuario que los controles de Windows Forms, que no lo necesitan.  
  
    > [!NOTE]
    >  Trabajar con un control ActiveX requiere el uso de un contenedor de interoperabilidad COM. Para más información, consulte [Interoperabilidad COM en Visual Basic y Visual C#](~/docs/visual-basic/programming-guide/com-interop/com-interoperability-in-net-framework-applications.md).  
  
    > [!NOTE]
    >  Si el nombre de un miembro del control ActiveX coincide con un nombre definido en .NET Framework, el importador de controles ActiveX agregará el prefijo con el nombre del miembro **Ctl** cuando crea el <xref:System.Windows.Forms.AxHost> clase derivada. Por ejemplo, si el control ActiveX tiene un miembro denominado **diseño**, se cambia el nombre **CtlLayout** en la clase derivada AxHost porque el **diseño** evento está definido en el. .NET Framework.  
  
## <a name="see-also"></a>Vea también

- [Cómo: Agregar controles ActiveX a formularios de Windows](how-to-add-activex-controls-to-windows-forms.md)
- [Seguridad de acceso del código](../../misc/code-access-security.md)
- [Comparación de los controles y objetos programables de distintos lenguajes y bibliotecas](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))
- [Insertar controles en Windows Forms](putting-controls-on-windows-forms.md)
- [Controles de formularios Windows Forms](index.md)
