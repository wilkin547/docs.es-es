---
title: "Cómo: Mostrar errores de validación en un diseñador hospedado en otro host"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5aa8fb53-8f75-433b-bc06-7c7d33583d5d
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b9f76f1ad5282ecf10a3ce58db0f6e1bd8df1b4d
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-display-validation-errors-in-a-rehosted-designer"></a>Cómo: Mostrar errores de validación en un diseñador hospedado en otro host
En este tema se describe cómo recuperar y publicar errores de validación en [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] hospedado en otro host. Esto proporciona un procedimiento para confirmar que un flujo de trabajo de un diseñador hospedado en otro host es válido.  
  
 Esta tarea tiene dos partes. La primera consiste en proporcionar una implementación de <xref:System.Activities.Presentation.Validation.IValidationErrorService>.  Hay un método crítico que se debe implementar en esta interfaz, <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A> que pasará una lista de los objetos <xref:System.Activities.Presentation.Validation.ValidationErrorInfo> que contienen información sobre los errores al registro de depuración.  Después de implementar la interfaz, la información de error se recupera publicando una instancia de esa implementación en el contexto de edición.  
  
### <a name="implement-the-ivalidationerrorservice-interface"></a>Implementar la interfaz IValidationErrorService  
  
1.  A continuación se incluye un ejemplo de código para una implementación sencilla que escribirá los errores de validación en el registro de depuración.  
  
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
  
1.  A continuación se incluye el código que publicará esto en el contexto de edición.  
  
    ```  
    wd.Context.Services.Publish<IValidationErrorService>(new DebugValidationErrorService());  
    ```
