---
title: -addmodule (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /addmodule
helpviewer_keywords:
- /addmodule compiler option [C#]
- -addmodule compiler option [C#]
- addmodule compiler option [C#]
ms.assetid: ed604546-0dc2-4bd4-9a3e-610a8d973e58
ms.openlocfilehash: 39955d86085b49ef503ea9ed531df9feafa648ac
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43524593"
---
# <a name="-addmodule-c-compiler-options"></a>-addmodule (Opciones del compilador de C#)
Esta opción agrega un módulo que se ha creado con el modificador target:module para la compilación actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-addmodule:file[;file2]  
```  
  
## <a name="arguments"></a>Argumentos  
 `file`, `file2`  
 Un archivo de salida que contiene metadatos. El archivo no puede contener un manifiesto de ensamblado. Para importar más de un archivo, hay que separar los nombres de archivo con una coma o un punto y coma.  
  
## <a name="remarks"></a>Comentarios  
 Todos los módulos agregados mediante **-addmodule** deben encontrarse en el mismo directorio que el archivo de salida en tiempo de ejecución. Es decir, puede especificar un módulo de cualquier directorio en el momento de la compilación, pero el módulo debe encontrarse en el directorio de la aplicación en tiempo de ejecución. Si dicho módulo no se encuentra en el directorio de la aplicación en tiempo de ejecución, obtendrá <xref:System.TypeLoadException>.  
  
 `file` no puede contener ningún ensamblado. Por ejemplo, si el archivo de salida se ha creado con [-target:module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md), se pueden importar sus metadatos con **-addmodule**.  
  
 Si se ha creado el archivo de salida con una opción **-target** diferente de **-target:module**, no se podrán importar sus metadatos con **-addmodule**, pero sí con [-reference](../../../csharp/language-reference/compiler-options/reference-compiler-option.md).  
  
 Esta opción del compilador no está disponible en Visual Studio; en un proyecto no se puede hacer referencia a un módulo. Además, esta opción del compilador no se puede modificar mediante programación.  
  
## <a name="example"></a>Ejemplo  
 Compile el archivo de código fuente `input.cs` y agregue metadatos de `metad1.netmodule` y `metad2.netmodule` para generar `out.exe`:  
  
```console  
csc -addmodule:metad1.netmodule;metad2.netmodule -out:out.exe input.cs  
```  
  
## <a name="see-also"></a>Vea también  

- [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)  
- [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)  
- [Ensamblados de múltiples archivos](../../../framework/app-domains/multifile-assemblies.md)  
- [Compilar un ensamblado de varios archivos](../../../framework/app-domains/how-to-build-a-multifile-assembly.md)
