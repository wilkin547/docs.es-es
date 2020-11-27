---
title: Procedimiento para mostrar errores de validación en un diseñador hospedado en otro host
ms.date: 03/30/2017
ms.assetid: 5aa8fb53-8f75-433b-bc06-7c7d33583d5d
ms.openlocfilehash: ccdb8941f46683dd1fd12387c0c5db2abe1d8dec
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280044"
---
# <a name="how-to-display-validation-errors-in-a-rehosted-designer"></a>Procedimiento para mostrar errores de validación en un diseñador hospedado en otro host

En este tema se describe cómo recuperar y publicar errores de validación en una Diseñador de flujo de trabajo de Windows hospedada en otro host. Esto proporciona un procedimiento para confirmar que un flujo de trabajo de un diseñador hospedado en otro host es válido.  
  
 Esta tarea tiene dos partes. La primera consiste en proporcionar una implementación de <xref:System.Activities.Presentation.Validation.IValidationErrorService>.  Hay un método crítico que se debe implementar en esta interfaz, <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A> que pasará una lista de los objetos <xref:System.Activities.Presentation.Validation.ValidationErrorInfo> que contienen información sobre los errores al registro de depuración.  Después de implementar la interfaz, la información de error se recupera publicando una instancia de esa implementación en el contexto de edición.  
  
### <a name="implement-the-ivalidationerrorservice-interface"></a>Implementar la interfaz IValidationErrorService  
  
1. A continuación se incluye un ejemplo de código para una implementación sencilla que escribirá los errores de validación en el registro de depuración.  
  
    ```csharp  
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
                errors.ToList().ForEach(vei => Debug.WriteLine($"Error: {vei.Message}"));  
            }  
        }  
    }  
    ```  
  
### <a name="publishing-to-the-editing-context"></a>Publicar en el contexto de edición  
  
1. A continuación se incluye el código que publicará esto en el contexto de edición.  
  
    ```csharp  
    wd.Context.Services.Publish<IValidationErrorService>(new DebugValidationErrorService());  
    ```
