---
title: Implementación de un proveedor de configuración personalizado en .NET
description: Obtenga información sobre cómo implementar un proveedor de configuración personalizado en aplicaciones .NET.
author: IEvangelist
ms.author: dapine
ms.date: 12/04/2020
ms.topic: how-to
ms.openlocfilehash: 22e46b7df8b02421633d6be251d990879baa8b2b
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "102402194"
---
# <a name="implement-a-custom-configuration-provider-in-net"></a><span data-ttu-id="4b8b3-103">Implementación de un proveedor de configuración personalizado en .NET</span><span class="sxs-lookup"><span data-stu-id="4b8b3-103">Implement a custom configuration provider in .NET</span></span>

<span data-ttu-id="4b8b3-104">Hay muchos [proveedores de configuración](configuration-providers.md) disponibles para orígenes de configuración comunes, como archivos JSON, XML e INI.</span><span class="sxs-lookup"><span data-stu-id="4b8b3-104">There are many [configuration providers](configuration-providers.md) available for common configuration sources such as JSON, XML, and INI files.</span></span> <span data-ttu-id="4b8b3-105">Puede que tenga que implementar un proveedor de configuración personalizado cuando uno de los proveedores disponibles no satisfaga las necesidades de su aplicación.</span><span class="sxs-lookup"><span data-stu-id="4b8b3-105">You may need to implement a custom configuration provider when one of the available providers doesn't suit your application needs.</span></span> <span data-ttu-id="4b8b3-106">En este artículo, aprenderá a implementar un proveedor de configuración personalizado que depende de una base de datos como origen de configuración.</span><span class="sxs-lookup"><span data-stu-id="4b8b3-106">In this article, you'll learn how to implement a custom configuration provider that relies on a database as its configuration source.</span></span>

## <a name="custom-configuration-provider"></a><span data-ttu-id="4b8b3-107">Proveedores de configuración personalizada</span><span class="sxs-lookup"><span data-stu-id="4b8b3-107">Custom configuration provider</span></span>

<span data-ttu-id="4b8b3-108">La aplicación de ejemplo muestra cómo crear un proveedor de configuración básica que lee los pares clave-valor de configuración desde una base de datos mediante [Entity Framework (EF) Core](/ef/core).</span><span class="sxs-lookup"><span data-stu-id="4b8b3-108">The sample app demonstrates how to create a basic configuration provider that reads configuration key-value pairs from a database using [Entity Framework (EF) Core](/ef/core).</span></span>

<span data-ttu-id="4b8b3-109">El proveedor tiene las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="4b8b3-109">The provider has the following characteristics:</span></span>

- <span data-ttu-id="4b8b3-110">La base de datos en memoria de EF se usa para fines de demostración.</span><span class="sxs-lookup"><span data-stu-id="4b8b3-110">The EF in-memory database is used for demonstration purposes.</span></span> <span data-ttu-id="4b8b3-111">Para usar una base de datos que requiere una cadena de conexión, implemente un `ConfigurationBuilder` secundario para suministrar la cadena de conexión desde otro proveedor de configuración.</span><span class="sxs-lookup"><span data-stu-id="4b8b3-111">To use a database that requires a connection string, implement a secondary `ConfigurationBuilder` to supply the connection string from another configuration provider.</span></span>
- <span data-ttu-id="4b8b3-112">El proveedor lee una tabla de base de datos en la configuración en el inicio.</span><span class="sxs-lookup"><span data-stu-id="4b8b3-112">The provider reads a database table into configuration at startup.</span></span> <span data-ttu-id="4b8b3-113">El proveedor no consulta la base de datos por clave.</span><span class="sxs-lookup"><span data-stu-id="4b8b3-113">The provider doesn't query the database on a per-key basis.</span></span>
- <span data-ttu-id="4b8b3-114">La función de recarga en cambio no se implementa, por lo que actualizar la base de datos después del inicio de la aplicación no afecta a la configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4b8b3-114">Reload-on-change isn't implemented, so updating the database after the app starts has no effect on the app's configuration.</span></span>

<span data-ttu-id="4b8b3-115">Defina una entidad de tipo de registro `Settings` para almacenar los valores de configuración en la base de datos.</span><span class="sxs-lookup"><span data-stu-id="4b8b3-115">Define a `Settings` record type entity for storing configuration values in the database.</span></span> <span data-ttu-id="4b8b3-116">Por ejemplo, podría agregar un archivo *Settings.cs* en la carpeta *Modelos*:</span><span class="sxs-lookup"><span data-stu-id="4b8b3-116">For example, you could add a *Settings.cs* file in your *Models* folder:</span></span>

:::code language="csharp" source="snippets/configuration/custom-provider/Models/Settings.cs":::

<span data-ttu-id="4b8b3-117">Para obtener información sobre los tipos de registro, consulte [Tipos de registro en C# 9](../../csharp/whats-new/csharp-9.md#record-types).</span><span class="sxs-lookup"><span data-stu-id="4b8b3-117">For information on record types, see [Record types in C# 9](../../csharp/whats-new/csharp-9.md#record-types).</span></span>

<span data-ttu-id="4b8b3-118">Agregue un `EntityConfigurationContext` para almacenar y tener acceso a los valores configurados.</span><span class="sxs-lookup"><span data-stu-id="4b8b3-118">Add an `EntityConfigurationContext` to store and access the configured values.</span></span>

<span data-ttu-id="4b8b3-119">*Providers/EntityConfigurationContext.cs*:</span><span class="sxs-lookup"><span data-stu-id="4b8b3-119">*Providers/EntityConfigurationContext.cs*:</span></span>

:::code language="csharp" source="snippets/configuration/custom-provider/Providers/EntityConfigurationContext.cs":::

<span data-ttu-id="4b8b3-120">Cree una clase que implemente <xref:Microsoft.Extensions.Configuration.IConfigurationSource>.</span><span class="sxs-lookup"><span data-stu-id="4b8b3-120">Create a class that implements <xref:Microsoft.Extensions.Configuration.IConfigurationSource>.</span></span>

<span data-ttu-id="4b8b3-121">*Providers/EntityConfigurationSource.cs*:</span><span class="sxs-lookup"><span data-stu-id="4b8b3-121">*Providers/EntityConfigurationSource.cs*:</span></span>

:::code language="csharp" source="snippets/configuration/custom-provider/Providers/EntityConfigurationSource.cs":::

<span data-ttu-id="4b8b3-122">Cree el proveedor de configuración personalizado heredando de <xref:Microsoft.Extensions.Configuration.ConfigurationProvider>.</span><span class="sxs-lookup"><span data-stu-id="4b8b3-122">Create the custom configuration provider by inheriting from <xref:Microsoft.Extensions.Configuration.ConfigurationProvider>.</span></span> <span data-ttu-id="4b8b3-123">El proveedor de configuración inicializa la base de datos cuando está vacía.</span><span class="sxs-lookup"><span data-stu-id="4b8b3-123">The configuration provider initializes the database when it's empty.</span></span> <span data-ttu-id="4b8b3-124">Puesto que las claves de configuración no distinguen entre mayúsculas y minúsculas, el diccionario empleado para iniciar la base de datos se crea con el comparador que tampoco hace tal distinción ([StringComparer.OrdinalIgnoreCase](xref:System.StringComparer.OrdinalIgnoreCase)).</span><span class="sxs-lookup"><span data-stu-id="4b8b3-124">Since configuration keys are case-insensitive, the dictionary used to initialize the database is created with the case-insensitive comparer ([StringComparer.OrdinalIgnoreCase](xref:System.StringComparer.OrdinalIgnoreCase)).</span></span>

<span data-ttu-id="4b8b3-125">*Providers/EntityConfigurationProvider.cs*:</span><span class="sxs-lookup"><span data-stu-id="4b8b3-125">*Providers/EntityConfigurationProvider.cs*:</span></span>

:::code language="csharp" source="snippets/configuration/custom-provider/Providers/EntityConfigurationProvider.cs":::

<span data-ttu-id="4b8b3-126">Un método de extensión `AddEntityConfiguration` permite agregar el origen de configuración a una instancia de <xref:Microsoft.Extensions.Configuration.IConfigurationBuilder>.</span><span class="sxs-lookup"><span data-stu-id="4b8b3-126">An `AddEntityConfiguration` extension method permits adding the configuration source to a <xref:Microsoft.Extensions.Configuration.IConfigurationBuilder> instance.</span></span>

<span data-ttu-id="4b8b3-127">*Extensions/ConfigurationBuilderExtensions.cs*:</span><span class="sxs-lookup"><span data-stu-id="4b8b3-127">*Extensions/ConfigurationBuilderExtensions.cs*:</span></span>

:::code language="csharp" source="snippets/configuration/custom-provider/Extensions/ConfigurationBuilderExtensions.cs":::

<span data-ttu-id="4b8b3-128">En el código siguiente se muestra cómo puede usar el `EntityConfigurationProvider` personalizado en *Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="4b8b3-128">The following code shows how to use the custom `EntityConfigurationProvider` in *Program.cs*:</span></span>

:::code language="csharp" source="snippets/configuration/custom-provider/Program.cs" highlight="27-28":::

## <a name="see-also"></a><span data-ttu-id="4b8b3-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b8b3-129">See also</span></span>

- [<span data-ttu-id="4b8b3-130">Configuración en .NET</span><span class="sxs-lookup"><span data-stu-id="4b8b3-130">Configuration in .NET</span></span>](configuration.md)
- [<span data-ttu-id="4b8b3-131">Proveedores de configuración en .NET</span><span class="sxs-lookup"><span data-stu-id="4b8b3-131">Configuration providers in .NET</span></span>](configuration-providers.md)
