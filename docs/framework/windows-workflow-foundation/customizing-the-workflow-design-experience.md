---
title: Personalizar la experiencia de diseño del flujo de trabajo
ms.date: 03/30/2017
helpviewer_keywords:
- extending [WF], Workflow Designer
ms.assetid: 98135077-0f5d-4d16-9337-01094e843537
ms.openlocfilehash: 2d6ef24d00baa4df6dfc8e0af69c1d489b79a41f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945995"
---
# <a name="customizing-the-workflow-design-experience"></a>Personalizar la experiencia de diseño del flujo de trabajo

Los escenarios para diseñar las actividades personalizadas y para re-hospedar [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] se han simplificado enormemente en [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)]. El desarrollo y la implementación resultan ahora más fáciles y más flexibles. El cambio infraestructural clave es que el nuevo modelo de programación Diseñador de actividad se basa en Windows Presentation Foundation (WPF). Esto proporciona la capacidad de definir diseñadores de actividad mediante declaración y re-hospedar [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] en otras aplicaciones con relativa facilidad. Al realizar el rehospedaje, se puede desarrollar un editor de expresiones personalizado para admitir IntelliSense o un dominio de expresión simplificado. La integración con Windows Communication Foundation (WCF) se ha vuelto más uniforme con el uso de servicios de flujo de trabajo. Se pueden utilizar diseñadores de actividad personalizados y el árbol de elementos de modelo para mejorar las experiencias en tiempo de diseño en los diseñadores de flujo de trabajo rehospedados.

## <a name="in-this-section"></a>En esta sección

 [Uso de plantillas y diseñadores de actividad personalizados](using-custom-activity-designers-and-templates.md)

 Describe cómo crear diseñadores de actividad personalizados y plantillas.

 [Rehospedaje del Diseñador de flujo de trabajo](rehosting-the-workflow-designer.md)

 Describe cómo volver a hospedar el [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] fuera de Visual Studio y cómo mostrar errores de validación.

 [Utilización de un editor de expresiones personalizado](using-a-custom-expression-editor.md)

 Describe cómo implementar un editor de expresiones personalizado para usar con los diseñadores de flujo de trabajo rehospedados fuera de Visual Studio 2010.

## <a name="reference"></a>Referencia

<xref:System.Activities.Presentation.ActivityDesigner>

## <a name="see-also"></a>Vea también

- [Extensión de Windows Workflow Foundation](extend.md)
- [Diseñador](./samples/designer.md)
- [Diseñadores de actividad personalizados](./samples/custom-activity-designers.md)
- [Rehospedaje del diseñador](./samples/designer-rehosting.md)