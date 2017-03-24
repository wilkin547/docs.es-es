---
title: Comando dotnet-add reference | Microsoft Docs
description: "El comando dotnet-add reference constituye una opción práctica para agregar referencias entre proyectos."
keywords: dotnet-add, CLI, comando de la CLI, .NET Core
author: spboyer
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 5e2a3efd-443c-4f23-a1b1-a662a5387879
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 7d23377244cfe60730b50bd247209de6e90bec70
ms.lasthandoff: 03/07/2017

---
# <a name="dotnet-add-reference"></a>dotnet-add reference

## <a name="name"></a>Name

`dotnet-add reference`: agrega referencias entre proyectos.

## <a name="synopsis"></a>Sinopsis

```
dotnet add [project] reference [-f|--framework] <project_references>
dotnet add reference [-h|--help]
```

## <a name="description"></a>Descripción

El comando `dotnet add reference` constituye una opción práctica para agregar referencias de proyecto a un proyecto. Después de ejecutar el comando, los fragmentos [`<ProjectReference>`](https://docs.microsoft.com/visualstudio/msbuild/common-msbuild-project-items) se agregan al archivo del proyecto.

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a>Argumentos

`project`

Archivo del proyecto sobre el que actuar. Si no se especifica, el comando buscará uno en el directorio actual.

`project_references`

Referencias entre proyectos que se van a agregar. Puede especificar uno o varios proyectos. El patrón Glob se admite en terminales basados en Unix/Linux.

## <a name="options"></a>Opciones

`-h|--help`

Imprime una corta ayuda para el comando.

`-f|--framework <FRAMEWORK>`

Agrega referencias de proyecto solo cuando el destino es un marco específico.

## <a name="examples"></a>Ejemplos

Agregar una referencia de proyecto:

`dotnet add app/app.csproj reference lib/lib.csproj`

Agregar varias referencias de proyecto:

`dotnet add reference lib1/lib1.csproj lib2/lib2.csproj`

Agregar varias referencias de proyecto usando el patrón de uso de comodines en Linux/Unix:

`dotnet add app/app.csproj reference **/*.csproj`
