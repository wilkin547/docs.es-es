---
title: "C&#243;mo: Mostrar errores de validaci&#243;n en un dise&#241;ador hospedado en otro host | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5aa8fb53-8f75-433b-bc06-7c7d33583d5d
caps.latest.revision: 4
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 4
---
# C&#243;mo: Mostrar errores de validaci&#243;n en un dise&#241;ador hospedado en otro host
En este tema se describe cómo recuperar y publicar errores de validación en [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] hospedado en otro host.Esto proporciona un procedimiento para confirmar que un flujo de trabajo de un diseñador hospedado en otro host es válido.  
  
 Esta tarea tiene dos partes.La primera consiste en proporcionar una implementación de <xref:System.Activities.Presentation.Validation.IValidationErrorService>.Hay un método crítico que se debe implementar en esta interfaz, <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A> que pasará una lista de los objetos <xref:System.Activities.Presentation.Validation.ValidationErrorInfo> que contienen información sobre los errores al registro de depuración.Después de implementar la interfaz, la información de error se recupera publicando una instancia de esa implementación en el contexto de edición.  
  
### Implementar la interfaz IValidationErrorService  
  
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
  
### Publicar en el contexto de edición  
  
1.  A continuación se incluye el código que publicará esto en el contexto de edición.  
  
    ```  
  
    wd.Context.Services.Publish<IValidationErrorService>(new DebugValidationErrorService());  
    ```