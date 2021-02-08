---
description: 'Más información sobre: Cómo: Mostrar errores de validación en un diseñador hospedado en otro host'
title: Procedimiento para mostrar errores de validación en un diseñador hospedado en otro host
ms.date: 03/30/2017
ms.assetid: 5aa8fb53-8f75-433b-bc06-7c7d33583d5d
ms.openlocfilehash: 75ff45e6e9a81df96a9940ce21d1b160cab1000e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99777741"
---
# <a name="how-to-display-validation-errors-in-a-rehosted-designer"></a><span data-ttu-id="45a3a-103">Procedimiento para mostrar errores de validación en un diseñador hospedado en otro host</span><span class="sxs-lookup"><span data-stu-id="45a3a-103">How to: Display Validation Errors in a Rehosted Designer</span></span>

<span data-ttu-id="45a3a-104">En este tema se describe cómo recuperar y publicar errores de validación en una Diseñador de flujo de trabajo de Windows hospedada en otro host.</span><span class="sxs-lookup"><span data-stu-id="45a3a-104">This topic describes how to retrieve and publish validation errors in a rehosted Windows Workflow Designer.</span></span> <span data-ttu-id="45a3a-105">Esto proporciona un procedimiento para confirmar que un flujo de trabajo de un diseñador hospedado en otro host es válido.</span><span class="sxs-lookup"><span data-stu-id="45a3a-105">This provides us with a procedure to confirm that a workflow in a rehosted designer is valid.</span></span>  
  
 <span data-ttu-id="45a3a-106">Esta tarea tiene dos partes.</span><span class="sxs-lookup"><span data-stu-id="45a3a-106">This task has two parts.</span></span> <span data-ttu-id="45a3a-107">La primera consiste en proporcionar una implementación de <xref:System.Activities.Presentation.Validation.IValidationErrorService>.</span><span class="sxs-lookup"><span data-stu-id="45a3a-107">The first is to provide an implementation <xref:System.Activities.Presentation.Validation.IValidationErrorService>.</span></span>  <span data-ttu-id="45a3a-108">Hay un método crítico que se debe implementar en esta interfaz, <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A> que pasará una lista de los objetos <xref:System.Activities.Presentation.Validation.ValidationErrorInfo> que contienen información sobre los errores al registro de depuración.</span><span class="sxs-lookup"><span data-stu-id="45a3a-108">There is one critical method to implement on this interface, <xref:System.Activities.Presentation.Validation.IValidationErrorService.ShowValidationErrors%2A> which will pass you a list of <xref:System.Activities.Presentation.Validation.ValidationErrorInfo> objects containing information about the errors to the debug log.</span></span>  <span data-ttu-id="45a3a-109">Después de implementar la interfaz, la información de error se recupera publicando una instancia de esa implementación en el contexto de edición.</span><span class="sxs-lookup"><span data-stu-id="45a3a-109">After implementing the interface, you retrieve the error information by publishing an instance of that implementation to the editing context.</span></span>  
  
### <a name="implement-the-ivalidationerrorservice-interface"></a><span data-ttu-id="45a3a-110">Implementar la interfaz IValidationErrorService</span><span class="sxs-lookup"><span data-stu-id="45a3a-110">Implement the IValidationErrorService Interface</span></span>  
  
1. <span data-ttu-id="45a3a-111">A continuación se incluye un ejemplo de código para una implementación sencilla que escribirá los errores de validación en el registro de depuración.</span><span class="sxs-lookup"><span data-stu-id="45a3a-111">Here is a code sample for a simple implementation that will write out the validation errors to the debug log.</span></span>  
  
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
  
### <a name="publishing-to-the-editing-context"></a><span data-ttu-id="45a3a-112">Publicar en el contexto de edición</span><span class="sxs-lookup"><span data-stu-id="45a3a-112">Publishing to the Editing Context</span></span>  
  
1. <span data-ttu-id="45a3a-113">A continuación se incluye el código que publicará esto en el contexto de edición.</span><span class="sxs-lookup"><span data-stu-id="45a3a-113">Here is the code that will publish this to the editing context.</span></span>  
  
    ```csharp  
    wd.Context.Services.Publish<IValidationErrorService>(new DebugValidationErrorService());  
    ```
