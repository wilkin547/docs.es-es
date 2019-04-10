---
title: Filtrar para mostrar errores de validación en un diseñador hospedado en otro host
ms.date: 03/30/2017
ms.assetid: 5aa8fb53-8f75-433b-bc06-7c7d33583d5d
ms.openlocfilehash: a3d993f55bf130039905f1a6512a7ae104512432
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59310205"
---
# <a name="how-to-display-validation-errors-in-a-rehosted-designer"></a>Filtrar para mostrar errores de validación en un diseñador hospedado en otro host
En este tema se describe cómo recuperar y publicar errores de validación en [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] hospedado en otro host. Esto proporciona un procedimiento para confirmar que un flujo de trabajo de un diseñador hospedado en otro host es válido.  
  
 Esta tarea tiene dos partes. La primera consiste en proporcionar una implementación de <xref:System.Activities.Presentation.Validation.IValidationErrorService>.  Hay un método crítico que se debe implementar en esta interfaz, <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A> que pasará una lista de los objetos <xref:System.Activities.Presentation.Validation.ValidationErrorInfo> que contienen información sobre los errores al registro de depuración.  Después de implementar la interfaz, la información de error se recupera publicando una instancia de esa implementación en el contexto de edición.  
  
### <a name="implement-the-ivalidationerrorservice-interface"></a>Implementar la interfaz IValidationErrorService  
  
1. A continuación se incluye un ejemplo de código para una implementación sencilla que escribirá los errores de validación en el registro de depuración.  
  
    ```  
    using System.Activities.Presentation.Validation;  
    using System.Collections.Generic;  
    using System.Diagnostics;  
    using System.Linq;  
  
    namespace VariableFinderShell  
    {  
        class DebugValidationErrorService : IValidationErrorService  
        {  
            public void ShowValidationErrors(IList<ValidationErrorInfo> errors)  
            {  
                errors.ToList().ForEach(vei => Debug.WriteLine(string.Format("Error: {0} ", vei.Message)));  
            }  
        }  
    }  
    ```  
  
### <a name="publishing-to-the-editing-context"></a>Publicar en el contexto de edición  
  
1. A continuación se incluye el código que publicará esto en el contexto de edición.  
  
    ```  
    wd.Context.Services.Publish<IValidationErrorService>(new DebugValidationErrorService());  
    ```
