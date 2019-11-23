---
title: Formularios y validación
description: Aprenda a crear formularios con la validación del lado cliente en increíble.
author: danroth27
ms.author: daroth
ms.date: 09/19/2019
ms.openlocfilehash: c30db5e06d36a6d15301835fe782b21058a80592
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841958"
---
# <a name="forms-and-validation"></a><span data-ttu-id="1bb17-103">Formularios y validación</span><span class="sxs-lookup"><span data-stu-id="1bb17-103">Forms and validation</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="1bb17-104">El marco de trabajo de formularios Web Forms de ASP.NET incluye un conjunto de controles de servidor de validación que controlan la validación de los datos especificados por el usuario en un formulario (`RequiredFieldValidator`, `CompareValidator`, `RangeValidator`, etc.).</span><span class="sxs-lookup"><span data-stu-id="1bb17-104">The ASP.NET Web Forms framework includes a set of validation server controls that handle validating user input entered into a form (`RequiredFieldValidator`, `CompareValidator`, `RangeValidator`, and so on).</span></span> <span data-ttu-id="1bb17-105">El marco de trabajo de formularios Web Forms de ASP.NET también admite el enlace de modelos y la validación del modelo en función de las anotaciones de datos (`[Required]`, `[StringLength]`, `[Range]`, etc.).</span><span class="sxs-lookup"><span data-stu-id="1bb17-105">The ASP.NET Web Forms framework also supports model binding and validating the model based on data annotations (`[Required]`, `[StringLength]`, `[Range]`, and so on).</span></span> <span data-ttu-id="1bb17-106">La lógica de validación se puede aplicar tanto en el servidor como en el cliente mediante la validación basada en JavaScript discreta.</span><span class="sxs-lookup"><span data-stu-id="1bb17-106">The validation logic can be enforced both on the server and on the client using unobtrusive JavaScript-based validation.</span></span> <span data-ttu-id="1bb17-107">El control de servidor `ValidationSummary` se usa para mostrar un resumen de los errores de validación al usuario.</span><span class="sxs-lookup"><span data-stu-id="1bb17-107">The `ValidationSummary` server control is used to display a summary of the validation errors to the user.</span></span>

<span data-ttu-id="1bb17-108">Increíblemente es compatible con el uso compartido de la lógica de validación entre el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="1bb17-108">Blazor supports the sharing of validation logic between both the client and the server.</span></span> <span data-ttu-id="1bb17-109">ASP.NET proporciona implementaciones de JavaScript pregeneradas de muchas validaciones de servidor comunes.</span><span class="sxs-lookup"><span data-stu-id="1bb17-109">ASP.NET provides pre-built JavaScript implementations of many common server validations.</span></span> <span data-ttu-id="1bb17-110">En muchos casos, el desarrollador todavía tiene que escribir JavaScript para implementar completamente la lógica de validación específica de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1bb17-110">In many cases, the developer still has to write JavaScript to fully implement their app-specific validation logic.</span></span> <span data-ttu-id="1bb17-111">Se pueden usar los mismos tipos de modelo, anotaciones de datos y lógica de validación tanto en el servidor como en el cliente.</span><span class="sxs-lookup"><span data-stu-id="1bb17-111">The same model types, data annotations, and validation logic can be used on both the server and client.</span></span>

<span data-ttu-id="1bb17-112">Increíbles proporciona un conjunto de componentes de entrada.</span><span class="sxs-lookup"><span data-stu-id="1bb17-112">Blazor provides a set of input components.</span></span> <span data-ttu-id="1bb17-113">Los componentes de entrada controlan los datos de campo de enlace a un modelo y validan la entrada del usuario cuando se envía el formulario.</span><span class="sxs-lookup"><span data-stu-id="1bb17-113">The input components handle binding field data to a model and validating the user input when the form is submitted.</span></span>

|<span data-ttu-id="1bb17-114">Componente de entrada</span><span class="sxs-lookup"><span data-stu-id="1bb17-114">Input component</span></span>|<span data-ttu-id="1bb17-115">Elemento HTML representado</span><span class="sxs-lookup"><span data-stu-id="1bb17-115">Rendered HTML element</span></span>    |
|---------------|-------------------------|
|`InputCheckbox`|`<input type="checkbox">`|
|`InputDate`    |`<input type="date">`    |
|`InputNumber`  |`<input type="number">`  |
|`InputSelect`  |`<select>`               |
|`InputText`    |`<input>`                |
|`InputTextArea`|`<textarea>`             |

<span data-ttu-id="1bb17-116">El componente `EditForm` ajusta estos componentes de entrada y organiza el proceso de validación a través de un `EditContext`.</span><span class="sxs-lookup"><span data-stu-id="1bb17-116">The `EditForm` component wraps these input components and orchestrates the validation process through an `EditContext`.</span></span> <span data-ttu-id="1bb17-117">Al crear una `EditForm`, se especifica la instancia de modelo a la que se va a enlazar mediante el parámetro `Model`.</span><span class="sxs-lookup"><span data-stu-id="1bb17-117">When creating an `EditForm`, you specify what model instance to bind to using the `Model` parameter.</span></span> <span data-ttu-id="1bb17-118">La validación se realiza normalmente con anotaciones de datos y es extensible.</span><span class="sxs-lookup"><span data-stu-id="1bb17-118">Validation is typically done using data annotations, and it's extensible.</span></span> <span data-ttu-id="1bb17-119">Para habilitar la validación basada en anotaciones de datos, agregue el componente `DataAnnotationsValidator` como un elemento secundario del `EditForm`.</span><span class="sxs-lookup"><span data-stu-id="1bb17-119">To enable data annotation-based validation, add the `DataAnnotationsValidator` component as a child of the `EditForm`.</span></span> <span data-ttu-id="1bb17-120">El componente `EditForm` proporciona un evento práctico para controlar los envíos válidos (`OnValidSubmit`) y no válidos (`OnInvalidSubmit`).</span><span class="sxs-lookup"><span data-stu-id="1bb17-120">The `EditForm` component provides a convenient event for handling valid (`OnValidSubmit`) and invalid (`OnInvalidSubmit`) submissions.</span></span> <span data-ttu-id="1bb17-121">También hay un evento más genérico `OnSubmit` que le permite desencadenar y controlar la validación.</span><span class="sxs-lookup"><span data-stu-id="1bb17-121">There's also a more generic `OnSubmit` event that lets you trigger and handle the validation yourself.</span></span>

<span data-ttu-id="1bb17-122">Para mostrar un resumen de errores de validación, utilice el componente `ValidationSummary`.</span><span class="sxs-lookup"><span data-stu-id="1bb17-122">To display a validation error summary, use the `ValidationSummary` component.</span></span> <span data-ttu-id="1bb17-123">Para mostrar los mensajes de validación de un campo de entrada concreto, use el componente `ValidationMessage`, especificando una expresión lambda para el parámetro `For` que apunta al miembro del modelo adecuado.</span><span class="sxs-lookup"><span data-stu-id="1bb17-123">To display validation messages for a specific input field, use the `ValidationMessage` component, specifying a lambda expression for the `For` parameter that points to the appropriate model member.</span></span>

<span data-ttu-id="1bb17-124">El siguiente tipo de modelo define varias reglas de validación mediante anotaciones de datos:</span><span class="sxs-lookup"><span data-stu-id="1bb17-124">The following model type defines several validation rules using data annotations:</span></span>

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

<span data-ttu-id="1bb17-125">En el componente siguiente se muestra cómo crear un formulario en extraordinariamente basado en el tipo de modelo de `Starship`:</span><span class="sxs-lookup"><span data-stu-id="1bb17-125">The following component demonstrates building a form in Blazor based on the `Starship` model type:</span></span>

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

<span data-ttu-id="1bb17-126">Después del envío del formulario, los datos enlazados al modelo no se han guardado en ningún almacén de datos, como una base de datos.</span><span class="sxs-lookup"><span data-stu-id="1bb17-126">After the form submission, the model-bound data hasn't been saved to any data store, like a database.</span></span> <span data-ttu-id="1bb17-127">En una aplicación increíblemente webassembly, los datos se deben enviar al servidor.</span><span class="sxs-lookup"><span data-stu-id="1bb17-127">In a Blazor WebAssembly app, the data must be sent to the server.</span></span> <span data-ttu-id="1bb17-128">Por ejemplo, mediante una solicitud HTTP POST.</span><span class="sxs-lookup"><span data-stu-id="1bb17-128">For example, using an HTTP POST request.</span></span> <span data-ttu-id="1bb17-129">En una aplicación de servidor más brillante, los datos ya están en el servidor, pero debe conservarse.</span><span class="sxs-lookup"><span data-stu-id="1bb17-129">In a Blazor Server app, the data is already on the server, but it must be persisted.</span></span> <span data-ttu-id="1bb17-130">Controlar el acceso a los datos en aplicaciones increíbles es el asunto de la sección tratamiento de los [datos](data.md) .</span><span class="sxs-lookup"><span data-stu-id="1bb17-130">Handling data access in Blazor apps is the subject of the [Dealing with data](data.md) section.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="1bb17-131">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="1bb17-131">Additional resources</span></span>

<span data-ttu-id="1bb17-132">Para obtener más información sobre los [formularios y la validación](/aspnet/core/blazor/forms-validation) en aplicaciones increíbles, consulte la documentación de extraordinarias.</span><span class="sxs-lookup"><span data-stu-id="1bb17-132">For more information on [forms and validation](/aspnet/core/blazor/forms-validation) in Blazor apps, see the Blazor documentation.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="1bb17-133">[Anterior](state-management.md)
>[Siguiente](data.md)</span><span class="sxs-lookup"><span data-stu-id="1bb17-133">[Previous](state-management.md)
[Next](data.md)</span></span>
