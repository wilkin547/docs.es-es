---
description: -bugreport (Opciones del compilador de C#)
title: -bugreport (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /bugreport
helpviewer_keywords:
- /bugreport compiler option [C#]
- -bugreport compiler option [C#]
- bugreport compiler option [C#]
ms.assetid: f39665e3-4f6f-4357-88a2-3274c7bec0c1
ms.openlocfilehash: 2afab44eec0c7bcc9809b458be0348093cb6dd07
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91196824"
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
  
## <a name="remarks"></a>Observaciones  

 La opción **-bugreport** especifica que la siguiente información debe colocarse en `file`:  
  
- Una copia de todos los archivos de código fuente de la compilación.  
  
- Una lista de las opciones del compilador que se han usado en la compilación.  
  
- Información de la versión sobre su compilador, tiempo de ejecución y sistema operativo.  
  
- Módulos y ensamblados a los que se hace referencia, guardados como dígitos hexadecimales, excepto los ensamblados que se proporcionan con .NET Framework y SDK.  
  
- Resultados del compilador, si los hay.  
  
- Una descripción del problema, que se le pedirá.  
  
- Una descripción de cómo cree que debe corregirse el problema, que se le pedirá.  
  
 Si esta opción se usa con **-errorreport:prompt** o **-errorreport:send**, la información del archivo se enviará a Microsoft Corporation.  
  
 Como una copia de todos los archivos de código fuente se colocarán en `file`, puede que quiera reproducir el defecto en el código sospechoso en el programa más corto posible.  
  
 Esta opción del compilador no está disponible en Visual Studio y no se puede cambiar mediante programación.  
  
 Tenga en cuenta que el contenido del código fuente expuesto del archivo generado puede provocar la divulgación de información involuntaria.  
  
## <a name="see-also"></a>Vea también

- [Opciones del compilador de C#](./index.md)
- [-errorreport (Opciones del compilador de C#)](./errorreport-compiler-option.md)
- [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
