---
title: -unsafe (Opciones del compilador de C#)
ms.date: 04/25/2018
f1_keywords:
- /unsafe
helpviewer_keywords:
- -unsafe compiler option [C#]
- unsafe compiler option [C#]
- /unsafe compiler option [C#]
ms.openlocfilehash: 146299fda103567b111c66400c17edf36addd843
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "65877994"
---
# <a name="-unsafe-c-compiler-options"></a>-unsafe (Opciones del compilador de C#)

La opción del compilador **-unsafe** permite la compilación de código en el que se usa la palabra clave [unsafe](../keywords/unsafe.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-unsafe  
```  
  
## <a name="remarks"></a>Comentarios

Para obtener más información sobre el código no seguro, vea [Código no seguro y punteros](../../programming-guide/unsafe-code-pointers/index.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1. Abra la página **Propiedades** del proyecto.  
  
2. Haga clic en la página de propiedades de **Compilar**.  
  
3. Active la casilla **Permitir código no seguro**.  
  
### <a name="to-add-this-option-in-a-csproj-file"></a>Para agregar esta opción en un archivo csproj

Abra el archivo .csproj de un proyecto y agregue los siguientes elementos:

```xml
  <PropertyGroup>
    <AllowUnsafeBlocks>true</AllowUnsafeBlocks>
  </PropertyGroup>
```

 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.AllowUnsafeBlocks%2A>.  
  
## <a name="example"></a>Ejemplo

Compile `in.cs` para el modo no seguro:  
  
```console  
csc -unsafe in.cs  
```  
  
## <a name="see-also"></a>Vea también

- [Opciones del compilador de C#](index.md)
- [Administrar propiedades de proyectos y de soluciones](/visualstudio/ide/managing-project-and-solution-properties)
