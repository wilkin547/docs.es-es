---
description: -debug (Opciones del compilador de C#)
title: -debug (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /debug
helpviewer_keywords:
- debug compiler option [C#]
- -debug compiler option [C#]
- /debug compiler option [C#]
ms.assetid: e2b48c07-01bc-45cc-a52c-92e9085eb969
ms.openlocfilehash: 164530a5ec99e7d5b9f34dbcdfb18d80f3102308
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/30/2020
ms.locfileid: "89125922"
---
# <a name="-debug-c-compiler-options"></a>-debug (Opciones del compilador de C#)
La opción **-debug** da lugar a que el compilador genere información de depuración y la incluya en el archivo o los archivos de salida.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-debug[+ | -]  
-debug:{full | pdbonly}  
```  
  
## <a name="arguments"></a>Argumentos  
 `+` &#124; `-`  
 Si se especifica `+`, o simplemente **-debug**, el compilador genera información de depuración y la incluye en una base de datos de programa (archivo .pdb). Si se especifica `-`, que es la opción predeterminada si no se especifica **-debug**, no se crea información de depuración.  
  
 `full` &#124; `pdbonly`  
 Especifica el tipo de información de depuración generado por el compilador. El argumento full, que es la opción predeterminada si no se especifica **-debug:pdbonly**, permite asociar un depurador al programa que se ejecuta. Al especificar la opción pdbonly, se permite depurar el código fuente cuando se inicia el programa en el depurador, pero solo muestra el ensamblador cuando el programa que se ejecuta está asociado al depurador.  
  
## <a name="remarks"></a>Comentarios  
 Use esta opción para crear versiones de depuración. Si no se especifica **-debug**, **-debug+** o **-debug:full**, no podrá depurar el archivo de salida del programa.  
  
 Si usa **-debug:full**, sea consciente de que se producirá algún impacto en la velocidad y el tamaño del código optimizado JIT y un pequeño impacto en la calidad del código con **-debug:full**. Recomendamos **-debug:pdbonly** o ningún PDB para generar el código de la versión de lanzamiento.  
  
> [!NOTE]
> Una diferencia entre **-debug:pdbonly** y **-debug:full** es que con **-debug:full** el compilador emite <xref:System.Diagnostics.DebuggableAttribute>, que se usa para indicar al compilador JIT que la información de depuración está disponible. Por consiguiente, aparecerá un error si el código contiene <xref:System.Diagnostics.DebuggableAttribute> establecido en false cuando se usa **-debug:full**.  
  
 Para obtener más información sobre cómo configurar el rendimiento de depuración de una aplicación, vea [Facilitar la depuración de una imagen](../../../framework/debug-trace-profile/making-an-image-easier-to-debug.md).  
  
 Para cambiar la ubicación del archivo .pdb, vea [-pdb (Opciones del compilador de C#)](./pdb-compiler-option.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1. Abra la página **Propiedades** del proyecto.  
  
2. Haga clic en la página de propiedades de **Compilar**.  
  
3. Haga clic en el botón **Avanzadas** .  
  
4. Modifique la propiedad **Información de depuración**.  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DebugSymbols%2A>.  
  
## <a name="example"></a>Ejemplo  
 Incluir información de depuración en el archivo de salida `app.pdb`:  
  
```console  
csc -debug -pdb:app.pdb test.cs  
```  
  
## <a name="see-also"></a>Vea también

- [Opciones del compilador de C#](./index.md)
- [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
