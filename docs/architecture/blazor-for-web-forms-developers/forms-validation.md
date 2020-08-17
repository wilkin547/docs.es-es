---
title: Formularios y validación
description: Aprenda a crear formularios con la validación del lado cliente en Blazor .
author: danroth27
ms.author: daroth
no-loc:
- Blazor
- Blazor WebAssembly
ms.date: 09/19/2019
ms.openlocfilehash: d2dce23996e996a736b04c9cdd1ccf3b549ff3ff
ms.sourcegitcommit: 0100be20fcf23f61dab672deced70059ed71bb2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2020
ms.locfileid: "88267560"
---
# <a name="forms-and-validation"></a>Formularios y validación

El marco de trabajo de formularios Web Forms de ASP.net incluye un conjunto de controles de servidor de validación que controlan la validación de los datos especificados por el usuario en un formulario ( `RequiredFieldValidator` , `CompareValidator` , `RangeValidator` , etc.). El marco de trabajo de formularios Web Forms de ASP.net también admite el enlace de modelos y la validación del modelo en función de las anotaciones de datos ( `[Required]` , `[StringLength]` , `[Range]` , etc.). La lógica de validación se puede aplicar tanto en el servidor como en el cliente mediante la validación basada en JavaScript discreta. El `ValidationSummary` control de servidor se usa para mostrar un resumen de los errores de validación al usuario.

Blazor admite el uso compartido de la lógica de validación entre el cliente y el servidor. ASP.NET proporciona implementaciones de JavaScript pregeneradas de muchas validaciones de servidor comunes. En muchos casos, el desarrollador todavía tiene que escribir JavaScript para implementar completamente la lógica de validación específica de la aplicación. Se pueden usar los mismos tipos de modelo, anotaciones de datos y lógica de validación tanto en el servidor como en el cliente.

Blazor proporciona un conjunto de componentes de entrada. Los componentes de entrada controlan los datos de campo de enlace a un modelo y validan la entrada del usuario cuando se envía el formulario.

|Componente de entrada|Elemento HTML representado    |
|---------------|-------------------------|
|`InputCheckbox`|`<input type="checkbox">`|
|`InputDate`    |`<input type="date">`    |
|`InputNumber`  |`<input type="number">`  |
|`InputSelect`  |`<select>`               |
|`InputText`    |`<input>`                |
|`InputTextArea`|`<textarea>`             |

El `EditForm` componente ajusta estos componentes de entrada y organiza el proceso de validación a través de un `EditContext` . Al crear un `EditForm` , se especifica la instancia de modelo a la que se va a enlazar mediante el `Model` parámetro. La validación se realiza normalmente con anotaciones de datos y es extensible. Para habilitar la validación basada en anotaciones de datos, agregue el `DataAnnotationsValidator` componente como un elemento secundario de `EditForm` . El `EditForm` componente proporciona un evento práctico para controlar los envíos válidos ( `OnValidSubmit` ) y no válidos ( `OnInvalidSubmit` ). También hay un evento más genérico `OnSubmit` que le permite desencadenar y controlar la validación.

Para mostrar un resumen de errores de validación, use el `ValidationSummary` componente. Para mostrar los mensajes de validación de un campo de entrada concreto, use el `ValidationMessage` componente, especificando una expresión lambda para el `For` parámetro que apunta al miembro del modelo adecuado.

El siguiente tipo de modelo define varias reglas de validación mediante anotaciones de datos:

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

El siguiente componente muestra cómo compilar un formulario en Blazor según el `Starship` tipo de modelo:

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

Después del envío del formulario, los datos enlazados al modelo no se han guardado en ningún almacén de datos, como una base de datos. En una Blazor WebAssembly aplicación de, los datos se deben enviar al servidor. Por ejemplo, mediante una solicitud HTTP POST. En una Blazor aplicación de servidor, los datos ya están en el servidor, pero debe conservarse. Controlar el acceso a Blazor los datos en las aplicaciones es el asunto de la sección tratamiento de los [datos](data.md) .

## <a name="additional-resources"></a>Recursos adicionales

Para obtener más información sobre los [formularios y la validación](/aspnet/core/blazor/forms-validation) en Blazor aplicaciones, vea la Blazor documentación de.

>[!div class="step-by-step"]
>[Anterior](state-management.md)
>[Siguiente](data.md)
