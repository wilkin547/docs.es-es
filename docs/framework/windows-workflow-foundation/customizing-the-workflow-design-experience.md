---
title: Personalizar la experiencia de diseño del flujo de trabajo
ms.date: 03/30/2017
helpviewer_keywords:
- extending [WF], Workflow Designer
ms.assetid: 98135077-0f5d-4d16-9337-01094e843537
ms.openlocfilehash: 27be398d874747b65ae051224070d3f40f1fbbb0
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715134"
---
# <a name="customizing-the-workflow-design-experience"></a>Personalizar la experiencia de diseño del flujo de trabajo

Los escenarios para diseñar actividades personalizadas y para rehospedar el Diseñador de flujo de trabajo de Windows se han simplificado en gran medida en .NET Framework 4. El desarrollo y la implementación resultan ahora más fáciles y más flexibles. El cambio de clave infraestructura es que el nuevo modelo de programación del diseñador de actividad se basa en Windows Presentation Foundation (WPF). Esto le ofrece la posibilidad de definir diseñadores de actividad de forma declarativa y de rehospedar el Diseñador de flujo de trabajo en otras aplicaciones con facilidad comparativa. Al realizar el rehospedaje, se puede desarrollar un editor de expresiones personalizado para admitir IntelliSense o un dominio de expresión simplificado. La integración con Windows Communication Foundation (WCF) ha vuelto a ser más fluida con el uso de los servicios de flujo de trabajo. Se pueden utilizar diseñadores de actividad personalizados y el árbol de elementos de modelo para mejorar las experiencias en tiempo de diseño en los diseñadores de flujo de trabajo rehospedados.

## <a name="in-this-section"></a>Esta sección

 [Uso de plantillas y diseñadores de actividad personalizados](using-custom-activity-designers-and-templates.md)

 Describe cómo crear diseñadores de actividad personalizados y plantillas.

 [Rehospedaje del Diseñador de flujo de trabajo](rehosting-the-workflow-designer.md)

 Describe cómo volver a hospedar el Diseñador de flujo de trabajo de Windows fuera de Visual Studio y cómo mostrar los errores de validación.

 [Utilización de un editor de expresiones personalizado](using-a-custom-expression-editor.md)

 Describe cómo implementar un editor de expresiones personalizado para usarlo con diseñadores de flujo de trabajo rehospedados fuera de Visual Studio 2010.

## <a name="reference"></a>Referencia

<xref:System.Activities.Presentation.ActivityDesigner>

## <a name="see-also"></a>Vea también

- [Extensión de Windows Workflow Foundation](extend.md)
- [Diseñador](./samples/designer.md)
- [Diseñadores de actividad personalizados](./samples/custom-activity-designers.md)
- [Rehospedaje del diseñador](./samples/designer-rehosting.md)
