---
title: Formularios y validación
description: Aprenda a crear formularios con la validación del lado cliente en Blazor .
author: danroth27
ms.author: daroth
no-loc:
- Blazor
- Blazor WebAssembly
ms.date: 09/19/2019
ms.openlocfilehash: 1a99719f59415872510aef051d1f3c73daf53e15
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "86173281"
---
# <a name="forms-and-validation"></a><span data-ttu-id="fa7ea-103">Formularios y validación</span><span class="sxs-lookup"><span data-stu-id="fa7ea-103">Forms and validation</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="fa7ea-104">El marco de trabajo de formularios Web Forms de ASP.net incluye un conjunto de controles de servidor de validación que controlan la validación de los datos especificados por el usuario en un formulario ( `RequiredFieldValidator` , `CompareValidator` , `RangeValidator` , etc.).</span><span class="sxs-lookup"><span data-stu-id="fa7ea-104">The ASP.NET Web Forms framework includes a set of validation server controls that handle validating user input entered into a form (`RequiredFieldValidator`, `CompareValidator`, `RangeValidator`, and so on).</span></span> <span data-ttu-id="fa7ea-105">El marco de trabajo de formularios Web Forms de ASP.net también admite el enlace de modelos y la validación del modelo en función de las anotaciones de datos ( `[Required]` , `[StringLength]` , `[Range]` , etc.).</span><span class="sxs-lookup"><span data-stu-id="fa7ea-105">The ASP.NET Web Forms framework also supports model binding and validating the model based on data annotations (`[Required]`, `[StringLength]`, `[Range]`, and so on).</span></span> <span data-ttu-id="fa7ea-106">La lógica de validación se puede aplicar tanto en el servidor como en el cliente mediante la validación basada en JavaScript discreta.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-106">The validation logic can be enforced both on the server and on the client using unobtrusive JavaScript-based validation.</span></span> <span data-ttu-id="fa7ea-107">El `ValidationSummary` control de servidor se usa para mostrar un resumen de los errores de validación al usuario.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-107">The `ValidationSummary` server control is used to display a summary of the validation errors to the user.</span></span>

Blazor<span data-ttu-id="fa7ea-108">admite el uso compartido de la lógica de validación entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-108"> supports the sharing of validation logic between both the client and the server.</span></span> <span data-ttu-id="fa7ea-109">ASP.NET proporciona implementaciones de JavaScript pregeneradas de muchas validaciones de servidor comunes.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-109">ASP.NET provides pre-built JavaScript implementations of many common server validations.</span></span> <span data-ttu-id="fa7ea-110">En muchos casos, el desarrollador todavía tiene que escribir JavaScript para implementar completamente la lógica de validación específica de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-110">In many cases, the developer still has to write JavaScript to fully implement their app-specific validation logic.</span></span> <span data-ttu-id="fa7ea-111">Se pueden usar los mismos tipos de modelo, anotaciones de datos y lógica de validación tanto en el servidor como en el cliente.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-111">The same model types, data annotations, and validation logic can be used on both the server and client.</span></span>

Blazor<span data-ttu-id="fa7ea-112">proporciona un conjunto de componentes de entrada.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-112"> provides a set of input components.</span></span> <span data-ttu-id="fa7ea-113">Los componentes de entrada controlan los datos de campo de enlace a un modelo y validan la entrada del usuario cuando se envía el formulario.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-113">The input components handle binding field data to a model and validating the user input when the form is submitted.</span></span>

|<span data-ttu-id="fa7ea-114">Componente de entrada</span><span class="sxs-lookup"><span data-stu-id="fa7ea-114">Input component</span></span>|<span data-ttu-id="fa7ea-115">Elemento HTML representado</span><span class="sxs-lookup"><span data-stu-id="fa7ea-115">Rendered HTML element</span></span>    |
|---------------|-------------------------|
|`InputCheckbox`|`<input type="checkbox">`|
|`InputDate`    |`<input type="date">`    |
|`InputNumber`  |`<input type="number">`  |
|`InputSelect`  |`<select>`               |
|`InputText`    |`<input>`                |
|`InputTextArea`|`<textarea>`             |

<span data-ttu-id="fa7ea-116">El `EditForm` componente ajusta estos componentes de entrada y organiza el proceso de validación a través de un `EditContext` .</span><span class="sxs-lookup"><span data-stu-id="fa7ea-116">The `EditForm` component wraps these input components and orchestrates the validation process through an `EditContext`.</span></span> <span data-ttu-id="fa7ea-117">Al crear un `EditForm` , se especifica la instancia de modelo a la que se va a enlazar mediante el `Model` parámetro.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-117">When creating an `EditForm`, you specify what model instance to bind to using the `Model` parameter.</span></span> <span data-ttu-id="fa7ea-118">La validación se realiza normalmente con anotaciones de datos y es extensible.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-118">Validation is typically done using data annotations, and it's extensible.</span></span> <span data-ttu-id="fa7ea-119">Para habilitar la validación basada en anotaciones de datos, agregue el `DataAnnotationsValidator` componente como un elemento secundario de `EditForm` .</span><span class="sxs-lookup"><span data-stu-id="fa7ea-119">To enable data annotation-based validation, add the `DataAnnotationsValidator` component as a child of the `EditForm`.</span></span> <span data-ttu-id="fa7ea-120">El `EditForm` componente proporciona un evento práctico para controlar los envíos válidos ( `OnValidSubmit` ) y no válidos ( `OnInvalidSubmit` ).</span><span class="sxs-lookup"><span data-stu-id="fa7ea-120">The `EditForm` component provides a convenient event for handling valid (`OnValidSubmit`) and invalid (`OnInvalidSubmit`) submissions.</span></span> <span data-ttu-id="fa7ea-121">También hay un evento más genérico `OnSubmit` que le permite desencadenar y controlar la validación.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-121">There's also a more generic `OnSubmit` event that lets you trigger and handle the validation yourself.</span></span>

<span data-ttu-id="fa7ea-122">Para mostrar un resumen de errores de validación, use el `ValidationSummary` componente.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-122">To display a validation error summary, use the `ValidationSummary` component.</span></span> <span data-ttu-id="fa7ea-123">Para mostrar los mensajes de validación de un campo de entrada concreto, use el `ValidationMessage` componente, especificando una expresión lambda para el `For` parámetro que apunta al miembro del modelo adecuado.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-123">To display validation messages for a specific input field, use the `ValidationMessage` component, specifying a lambda expression for the `For` parameter that points to the appropriate model member.</span></span>

<span data-ttu-id="fa7ea-124">El siguiente tipo de modelo define varias reglas de validación mediante anotaciones de datos:</span><span class="sxs-lookup"><span data-stu-id="fa7ea-124">The following model type defines several validation rules using data annotations:</span></span>

```csharp
using System;
using System.ComponentModel.DataAnnotations;

public class Starship
{
    [Required]
    [StringLength(16,
        ErrorMessage = "Identifier too long (16 character limit).")]
    public string Identifier { get; set; }

    public string Description { get; set; }

    [Required]
    public string Classification { get; set; }

    [Range(1, 100000,
        ErrorMessage = "Accommodation invalid (1-100000).")]
    public int MaximumAccommodation { get; set; }

    [Required]
    [Range(typeof(bool), "true", "true",
        ErrorMessage = "This form disallows unapproved ships.")]
    public bool IsValidatedDesign { get; set; }

    [Required]
    public DateTime ProductionDate { get; set; }
}
```

<span data-ttu-id="fa7ea-125">El siguiente componente muestra cómo compilar un formulario en Blazor según el `Starship` tipo de modelo:</span><span class="sxs-lookup"><span data-stu-id="fa7ea-125">The following component demonstrates building a form in Blazor based on the `Starship` model type:</span></span>

```razor
<h1>New Ship Entry Form</h1>

<EditForm Model="@starship" OnValidSubmit="@HandleValidSubmit">
    <DataAnnotationsValidator />
    <ValidationSummary />

    <p>
        <label for="identifier">Identifier: </label>
        <InputText id="identifier" @bind-Value="starship.Identifier" />
        <ValidationMessage For="() => starship.Identifier" />
    </p>
    <p>
        <label for="description">Description (optional): </label>
        <InputTextArea id="description" @bind-Value="starship.Description" />
    </p>
    <p>
        <label for="classification">Primary Classification: </label>
        <InputSelect id="classification" @bind-Value="starship.Classification">
            <option value="">Select classification ...</option>
            <option value="Exploration">Exploration</option>
            <option value="Diplomacy">Diplomacy</option>
            <option value="Defense">Defense</option>
        </InputSelect>
        <ValidationMessage For="() => starship.Classification" />
    </p>
    <p>
        <label for="accommodation">Maximum Accommodation: </label>
        <InputNumber id="accommodation" @bind-Value="starship.MaximumAccommodation" />
        <ValidationMessage For="() => starship.MaximumAccommodation" />
    </p>
    <p>
        <label for="valid">Engineering Approval: </label>
        <InputCheckbox id="valid" @bind-Value="starship.IsValidatedDesign" />
        <ValidationMessage For="() => starship.IsValidatedDesign" />
    </p>
    <p>
        <label for="productionDate">Production Date: </label>
        <InputDate id="productionDate" @bind-Value="starship.ProductionDate" />
        <ValidationMessage For="() => starship.ProductionDate" />
    </p>

    <button type="submit">Submit</button>
</EditForm>

@code {
    private Starship starship = new Starship();

    private void HandleValidSubmit()
    {
        // Save the data
    }
}
```

<span data-ttu-id="fa7ea-126">Después del envío del formulario, los datos enlazados al modelo no se han guardado en ningún almacén de datos, como una base de datos.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-126">After the form submission, the model-bound data hasn't been saved to any data store, like a database.</span></span> <span data-ttu-id="fa7ea-127">En una Blazor WebAssembly aplicación de, los datos se deben enviar al servidor.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-127">In a Blazor WebAssembly app, the data must be sent to the server.</span></span> <span data-ttu-id="fa7ea-128">Por ejemplo, mediante una solicitud HTTP POST.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-128">For example, using an HTTP POST request.</span></span> <span data-ttu-id="fa7ea-129">En una Blazor aplicación de servidor, los datos ya están en el servidor, pero debe conservarse.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-129">In a Blazor Server app, the data is already on the server, but it must be persisted.</span></span> <span data-ttu-id="fa7ea-130">Controlar el acceso a Blazor los datos en las aplicaciones es el asunto de la sección tratamiento de los [datos](data.md) .</span><span class="sxs-lookup"><span data-stu-id="fa7ea-130">Handling data access in Blazor apps is the subject of the [Dealing with data](data.md) section.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fa7ea-131">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="fa7ea-131">Additional resources</span></span>

<span data-ttu-id="fa7ea-132">Para obtener más información sobre los [formularios y la validación](/aspnet/core/blazor/forms-validation) en Blazor aplicaciones, vea la Blazor documentación de.</span><span class="sxs-lookup"><span data-stu-id="fa7ea-132">For more information on [forms and validation](/aspnet/core/blazor/forms-validation) in Blazor apps, see the Blazor documentation.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="fa7ea-133">[Anterior](state-management.md)
>[Siguiente](data.md)</span><span class="sxs-lookup"><span data-stu-id="fa7ea-133">[Previous](state-management.md)
[Next](data.md)</span></span>
