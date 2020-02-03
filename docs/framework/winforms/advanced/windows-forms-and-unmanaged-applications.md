---
title: Aplicaciones no administradas
ms.date: 03/30/2017
helpviewer_keywords:
- ActiveX controls [Windows Forms]
- COM interop [Windows Forms], Windows Forms
- COM [Windows Forms]
- Windows Forms, unmanaged
- Windows Forms, interop
ms.assetid: 81bc100c-fa49-4614-85a6-0f7ab59eac8a
ms.openlocfilehash: 17dc20653d1628dfd460a9891e1b0a21c0ebecbd
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746370"
---
# <a name="windows-forms-and-unmanaged-applications"></a>Aplicaciones de Windows Forms y aplicaciones no administradas
Los controles y aplicaciones de Windows Forms pueden interoperar con aplicaciones no administradas, con algunas advertencias. En las secciones siguientes se describen los escenarios y las configuraciones que las aplicaciones y los controles de Windows Forms admiten y no admiten.  
  
## <a name="in-this-section"></a>En esta sección  
 [Información general sobre formularios Windows Forms y aplicaciones no administradas](windows-forms-and-unmanaged-applications-overview.md)  
 Proporciona información general acerca de cómo utilizar e implementar controles de Windows Forms que funcionan con aplicaciones no administradas.  
  
 [Admitir la interoperabilidad COM al mostrar Windows Forms con el método ShowDialog](com-interop-by-displaying-a-windows-form-shadow.md)  
 Proporciona un ejemplo de código que muestra cómo utilizar el método <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> para ejecutar Windows Forms en una aplicación no administrada.  
  
 [How to: Support COM Interop by Displaying Each Windows Form on Its Own Thread](how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)  
 Proporciona un ejemplo de código que muestra cómo ejecutar Windows Forms en su propio subproceso.  
  
 Consulte también [Tutorial: Admitir la interoperabilidad COM al mostrar Windows Forms en su propio subproceso](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms233639(v=vs.100)).  
  
## <a name="reference"></a>Referencia  
 <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType>  
 Se utiliza para crear un subproceso independiente para Windows Forms.  
  
 <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType>  
 Inicia un bucle de mensajes para un subproceso.  
  
 <xref:System.Windows.Forms.Control.Invoke%2A>  
 Calcula las referencias de llamadas desde una aplicación no administrada a un formulario.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Exponer componentes de .NET Framework en COM](../../interop/exposing-dotnet-components-to-com.md)  
 Proporciona información general acerca de cómo utilizar tipos de .NET Framework en aplicaciones no administradas.
