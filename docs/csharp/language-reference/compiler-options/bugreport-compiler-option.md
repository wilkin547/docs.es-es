---
title: -bugreport (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /bugreport
helpviewer_keywords:
- /bugreport compiler option [C#]
- -bugreport compiler option [C#]
- bugreport compiler option [C#]
ms.assetid: f39665e3-4f6f-4357-88a2-3274c7bec0c1
ms.openlocfilehash: 6e4674acd2a5edbbffd2babf130d2078019ab9b7
ms.sourcegitcommit: a368166a51e5204c0224fbf5e46476e3ed122817
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2018
ms.locfileid: "43331740"
---
# <a name="-bugreport-c-compiler-options"></a>-bugreport (Opciones del compilador de C#)
Especifica que esa información de depuración debe colocarse en un archivo para su análisis posterior.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-bugreport:file  
```  
  
## <a name="arguments"></a>Argumentos  
 `file`  
 El nombre del archivo que quiere que contenga su informe de errores.  
  
## <a name="remarks"></a>Comentarios  
 La opción **-bugreport** especifica que la siguiente información debe colocarse en `file`:  
  
-   Una copia de todos los archivos de código fuente de la compilación.  
  
-   Una lista de las opciones del compilador que se han usado en la compilación.  
  
-   Información de la versión sobre su compilador, tiempo de ejecución y sistema operativo.  
  
-   Módulos y ensamblados a los que se hace referencia, guardados como dígitos hexadecimales, excepto los ensamblados que se proporcionan con .NET Framework y SDK.  
  
-   Resultados del compilador, si los hay.  
  
-   Una descripción del problema, que se le pedirá.  
  
-   Una descripción de cómo cree que debe corregirse el problema, que se le pedirá.  
  
 Si esta opción se usa con **-errorreport:prompt** o **-errorreport:send**, la información del archivo se enviará a Microsoft Corporation.  
  
 Como una copia de todos los archivos de código fuente se colocarán en `file`, puede que quiera reproducir el defecto en el código sospechoso en el programa más corto posible.  
  
 Esta opción del compilador no está disponible en Visual Studio y no se puede cambiar mediante programación.  
  
 Tenga en cuenta que el contenido del código fuente expuesto del archivo generado puede provocar la divulgación de información involuntaria.  
  
## <a name="see-also"></a>Vea también  

- [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)  
- [-errorreport (Opciones del compilador de C#)](../../../csharp/language-reference/compiler-options/errorreport-compiler-option.md)  
- [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
