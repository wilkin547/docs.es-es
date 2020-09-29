---
description: -main (Opciones del compilador de C#)
title: -main (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /main
helpviewer_keywords:
- -main compiler option [C#]
- main compiler option [C#]
- /main compiler option [C#]
ms.assetid: 975cf4d5-36ac-4530-826c-4aad0c7f2049
ms.openlocfilehash: c27898de2a7cc2f3c01c51f8de1122e81b2233b4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194120"
---
# <a name="-main-c-compiler-options"></a>-main (Opciones del compilador de C#)

Esta opción especifica la clase que contiene el punto de entrada al programa si hay más de una clase que contenga un método **Main**.

## <a name="syntax"></a>Sintaxis

```console
-main:class
```

## <a name="arguments"></a>Argumentos

 `class`  
 Tipo que contiene el método **Main**.  
 El nombre de clase proporcionado debe ser completo: debe incluir el espacio de nombres completo que contiene la clase, seguido del nombre de clase. Por ejemplo, cuando el método `Main` se encuentra dentro de la clase `Program` en el espacio de nombres `MyApplication.Core`, la opción del compilador tiene que ser `-main:MyApplication.Core.Program`.

## <a name="remarks"></a>Comentarios

Si la compilación incluye más de un tipo con un método [Main](../../programming-guide/main-and-command-args/index.md), puede especificar el tipo que contiene el método **Main** que quiere usar como punto de entrada en el programa.

Esta opción se usa al compilar un archivo *.exe*.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio

1. Abra la página **Propiedades** del proyecto.

2. Haga clic en la página de propiedades **Aplicación**.

3. Modifique la propiedad **Objeto de inicio**.

    Para establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.StartupObject%2A>.

### <a name="to-set-this-compiler-option-by-manually-editing-the-csproj-file"></a>Para establecer esta opción del compilador editando manualmente el archivo *.csproj*

Puede establecer esta opción editando el archivo. csproj y agregando un elemento `StartupObject` dentro de la sección `PropertyGroup`. Por ejemplo:

```xml
  <PropertyGroup>
    ...
    <StartupObject>MyApplication.Core.Program</StartupObject>
  </PropertyGroup>
```

## <a name="example"></a>Ejemplo

Compile `t2.cs` y `t3.cs` y especifique que el método **Main** se encuentra en `Test2`:

```console
csc t2.cs t3.cs -main:Test2
```

## <a name="see-also"></a>Vea también

- [Opciones del compilador de C#](./index.md)
- [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
