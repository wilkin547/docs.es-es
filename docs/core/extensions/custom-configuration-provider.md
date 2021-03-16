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
# <a name="implement-a-custom-configuration-provider-in-net"></a>Implementación de un proveedor de configuración personalizado en .NET

Hay muchos [proveedores de configuración](configuration-providers.md) disponibles para orígenes de configuración comunes, como archivos JSON, XML e INI. Puede que tenga que implementar un proveedor de configuración personalizado cuando uno de los proveedores disponibles no satisfaga las necesidades de su aplicación. En este artículo, aprenderá a implementar un proveedor de configuración personalizado que depende de una base de datos como origen de configuración.

## <a name="custom-configuration-provider"></a>Proveedores de configuración personalizada

La aplicación de ejemplo muestra cómo crear un proveedor de configuración básica que lee los pares clave-valor de configuración desde una base de datos mediante [Entity Framework (EF) Core](/ef/core).

El proveedor tiene las siguientes características:

- La base de datos en memoria de EF se usa para fines de demostración. Para usar una base de datos que requiere una cadena de conexión, implemente un `ConfigurationBuilder` secundario para suministrar la cadena de conexión desde otro proveedor de configuración.
- El proveedor lee una tabla de base de datos en la configuración en el inicio. El proveedor no consulta la base de datos por clave.
- La función de recarga en cambio no se implementa, por lo que actualizar la base de datos después del inicio de la aplicación no afecta a la configuración de la aplicación.

Defina una entidad de tipo de registro `Settings` para almacenar los valores de configuración en la base de datos. Por ejemplo, podría agregar un archivo *Settings.cs* en la carpeta *Modelos*:

:::code language="csharp" source="snippets/configuration/custom-provider/Models/Settings.cs":::

Para obtener información sobre los tipos de registro, consulte [Tipos de registro en C# 9](../../csharp/whats-new/csharp-9.md#record-types).

Agregue un `EntityConfigurationContext` para almacenar y tener acceso a los valores configurados.

*Providers/EntityConfigurationContext.cs*:

:::code language="csharp" source="snippets/configuration/custom-provider/Providers/EntityConfigurationContext.cs":::

Cree una clase que implemente <xref:Microsoft.Extensions.Configuration.IConfigurationSource>.

*Providers/EntityConfigurationSource.cs*:

:::code language="csharp" source="snippets/configuration/custom-provider/Providers/EntityConfigurationSource.cs":::

Cree el proveedor de configuración personalizado heredando de <xref:Microsoft.Extensions.Configuration.ConfigurationProvider>. El proveedor de configuración inicializa la base de datos cuando está vacía. Puesto que las claves de configuración no distinguen entre mayúsculas y minúsculas, el diccionario empleado para iniciar la base de datos se crea con el comparador que tampoco hace tal distinción ([StringComparer.OrdinalIgnoreCase](xref:System.StringComparer.OrdinalIgnoreCase)).

*Providers/EntityConfigurationProvider.cs*:

:::code language="csharp" source="snippets/configuration/custom-provider/Providers/EntityConfigurationProvider.cs":::

Un método de extensión `AddEntityConfiguration` permite agregar el origen de configuración a una instancia de <xref:Microsoft.Extensions.Configuration.IConfigurationBuilder>.

*Extensions/ConfigurationBuilderExtensions.cs*:

:::code language="csharp" source="snippets/configuration/custom-provider/Extensions/ConfigurationBuilderExtensions.cs":::

En el código siguiente se muestra cómo puede usar el `EntityConfigurationProvider` personalizado en *Program.cs*:

:::code language="csharp" source="snippets/configuration/custom-provider/Program.cs" highlight="27-28":::

## <a name="see-also"></a>Vea también

- [Configuración en .NET](configuration.md)
- [Proveedores de configuración en .NET](configuration-providers.md)
