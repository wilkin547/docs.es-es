---
title: Aplicaciones de Windows Forms y aplicaciones no administradas
ms.date: 03/30/2017
helpviewer_keywords:
- ActiveX controls [Windows Forms]
- COM interop [Windows Forms], Windows Forms
- COM [Windows Forms]
- Windows Forms, unmanaged
- Windows Forms, interop
ms.assetid: 81bc100c-fa49-4614-85a6-0f7ab59eac8a
ms.openlocfilehash: bc0c848d1c92871dacab93497c674645f3ac83fe
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43560327"
---
# <a name="windows-forms-and-unmanaged-applications"></a>Aplicaciones de Windows Forms y aplicaciones no administradas
Los controles y aplicaciones de Windows Forms pueden interoperar con aplicaciones no administradas, con algunas advertencias. En las secciones siguientes se describen los escenarios y las configuraciones que las aplicaciones y los controles de Windows Forms admiten y no admiten.  
  
## <a name="in-this-section"></a>En esta sección  
 [Información general sobre formularios Windows Forms y aplicaciones no administradas](../../../../docs/framework/winforms/advanced/windows-forms-and-unmanaged-applications-overview.md)  
 Proporciona información general acerca de cómo utilizar e implementar controles de Windows Forms que funcionan con aplicaciones no administradas.  
  
 [Admitir la interoperabilidad COM al mostrar Windows Forms con el método ShowDialog](../../../../docs/framework/winforms/advanced/com-interop-by-displaying-a-windows-form-shadow.md)  
 Proporciona un ejemplo de código que muestra cómo utilizar el método <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> para ejecutar Windows Forms en una aplicación no administrada.  
  
 [Cómo: Admitir la interoperabilidad COM al mostrar Windows Forms en sus propios subprocesos](../../../../docs/framework/winforms/advanced/how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)  
 Proporciona un ejemplo de código que muestra cómo ejecutar Windows Forms en su propio subproceso.  
  
 Consulte también [Tutorial: compatibilidad con COM Interop by Displaying Each Windows Form on Its Own Thread](https://msdn.microsoft.com/library/ms233639\(v=vs.110\)).  
  
## <a name="reference"></a>Referencia  
 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType>  
 Se utiliza para crear un subproceso independiente para Windows Forms.  
  
 <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType>  
 Inicia un bucle de mensajes para un subproceso.  
  
 <xref:System.Windows.Forms.Control.Invoke%2A>  
 Calcula las referencias de llamadas desde una aplicación no administrada a un formulario.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Exponer componentes de .NET Framework en COM](../../../../docs/framework/interop/exposing-dotnet-components-to-com.md)  
 Proporciona información general acerca de cómo utilizar tipos de .NET Framework en aplicaciones no administradas.
