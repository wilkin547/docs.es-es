---
description: Más información sobre cómo personalizar la experiencia de diseño de flujo de trabajo
title: Personalizar la experiencia de diseño del flujo de trabajo
ms.date: 03/30/2017
helpviewer_keywords:
- extending [WF], Workflow Designer
ms.assetid: 98135077-0f5d-4d16-9337-01094e843537
ms.openlocfilehash: 02049f8b42de3de6e4dfdfe8a4151be1500bcca9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99742659"
---
# <a name="customizing-the-workflow-design-experience"></a>Personalizar la experiencia de diseño del flujo de trabajo

Los escenarios para diseñar actividades personalizadas y para rehospedar el Diseñador de flujo de trabajo de Windows se han simplificado en gran medida en .NET Framework 4. El desarrollo y la implementación resultan ahora más fáciles y más flexibles. El cambio de clave infraestructura es que el nuevo modelo de programación del diseñador de actividad se basa en Windows Presentation Foundation (WPF). Esto le ofrece la posibilidad de definir diseñadores de actividad de forma declarativa y de rehospedar el Diseñador de flujo de trabajo en otras aplicaciones con facilidad comparativa. Al realizar el rehospedaje, se puede desarrollar un editor de expresiones personalizado para admitir IntelliSense o un dominio de expresión simplificado. La integración con Windows Communication Foundation (WCF) ha vuelto a ser más fluida con el uso de los servicios de flujo de trabajo. Se pueden utilizar diseñadores de actividad personalizados y el árbol de elementos de modelo para mejorar las experiencias en tiempo de diseño en los diseñadores de flujo de trabajo rehospedados.

## <a name="in-this-section"></a>En esta sección

 [Usar plantillas y diseñadores de actividad personalizados](using-custom-activity-designers-and-templates.md)

 Describe cómo crear diseñadores de actividad personalizados y plantillas.

 [Rehospedar el Diseñador de flujo de trabajo](rehosting-the-workflow-designer.md)

 Describe cómo volver a hospedar el Diseñador de flujo de trabajo de Windows fuera de Visual Studio y cómo mostrar los errores de validación.

 [Usar un editor de expresiones personalizado](using-a-custom-expression-editor.md)

 Describe cómo implementar un editor de expresiones personalizado para usarlo con diseñadores de flujo de trabajo rehospedados fuera de Visual Studio 2010.

## <a name="reference"></a>Referencia

<xref:System.Activities.Presentation.ActivityDesigner>

## <a name="see-also"></a>Vea también

- [Ampliar Windows Workflow Foundation](extend.md)
- [Designer](./samples/designer.md)
- [Diseñadores de actividad personalizados](./samples/custom-activity-designers.md)
- [Rehost del diseñador](./samples/designer-rehosting.md)
