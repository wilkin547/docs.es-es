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
# <a name="how-to-display-validation-errors-in-a-rehosted-designer"></a><span data-ttu-id="722f7-102">Cómo: Mostrar errores de validación en un diseñador hospedado en otro host</span><span class="sxs-lookup"><span data-stu-id="722f7-102">How to: Display Validation Errors in a Rehosted Designer</span></span>
<span data-ttu-id="722f7-103">En este tema se describe cómo recuperar y publicar errores de validación en [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] hospedado en otro host.</span><span class="sxs-lookup"><span data-stu-id="722f7-103">This topic describes how to retrieve and publish validation errors in a rehosted [!INCLUDE[wfd1](../../../includes/wfd1-md.md)].</span></span> <span data-ttu-id="722f7-104">Esto proporciona un procedimiento para confirmar que un flujo de trabajo de un diseñador hospedado en otro host es válido.</span><span class="sxs-lookup"><span data-stu-id="722f7-104">This provides us with a procedure to confirm that a workflow in a rehosted designer is valid.</span></span>  
  
 <span data-ttu-id="722f7-105">Esta tarea tiene dos partes.</span><span class="sxs-lookup"><span data-stu-id="722f7-105">This task has two parts.</span></span> <span data-ttu-id="722f7-106">La primera consiste en proporcionar una implementación de <xref:System.Activities.Presentation.Validation.IValidationErrorService>.</span><span class="sxs-lookup"><span data-stu-id="722f7-106">The first is to provide an implementation <xref:System.Activities.Presentation.Validation.IValidationErrorService>.</span></span>  <span data-ttu-id="722f7-107">Hay un método crítico que se debe implementar en esta interfaz, <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A> que pasará una lista de los objetos <xref:System.Activities.Presentation.Validation.ValidationErrorInfo> que contienen información sobre los errores al registro de depuración.</span><span class="sxs-lookup"><span data-stu-id="722f7-107">There is one critical method to implement on this interface, <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A> which will pass you a list of <xref:System.Activities.Presentation.Validation.ValidationErrorInfo> objects containing information about the errors to the debug log.</span></span>  <span data-ttu-id="722f7-108">Después de implementar la interfaz, la información de error se recupera publicando una instancia de esa implementación en el contexto de edición.</span><span class="sxs-lookup"><span data-stu-id="722f7-108">After implementing the interface, you retrieve the error information by publishing an instance of that implementation to the editing context.</span></span>  
  
### <a name="implement-the-ivalidationerrorservice-interface"></a><span data-ttu-id="722f7-109">Implementar la interfaz IValidationErrorService</span><span class="sxs-lookup"><span data-stu-id="722f7-109">Implement the IValidationErrorService Interface</span></span>  
  
1.  <span data-ttu-id="722f7-110">A continuación se incluye un ejemplo de código para una implementación sencilla que escribirá los errores de validación en el registro de depuración.</span><span class="sxs-lookup"><span data-stu-id="722f7-110">Here is a code sample for a simple implementation that will write out the validation errors to the debug log.</span></span>  
  
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
  
### <a name="publishing-to-the-editing-context"></a><span data-ttu-id="722f7-111">Publicar en el contexto de edición</span><span class="sxs-lookup"><span data-stu-id="722f7-111">Publishing to the Editing Context</span></span>  
  
1.  <span data-ttu-id="722f7-112">A continuación se incluye el código que publicará esto en el contexto de edición.</span><span class="sxs-lookup"><span data-stu-id="722f7-112">Here is the code that will publish this to the editing context.</span></span>  
  
    ```  
    wd.Context.Services.Publish<IValidationErrorService>(new DebugValidationErrorService());  
    ```
