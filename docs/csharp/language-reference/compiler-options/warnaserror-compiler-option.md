---
description: -warnaserror (Opciones del compilador de C#)
title: -warnaserror (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /warnaserror
helpviewer_keywords:
- /warnaserror compiler option [C#]
- -warnaserror compiler option [C#]
- warnaserror compiler option [C#]
ms.assetid: 04680ec3-08d6-4e2e-a274-38310e10e33c
ms.openlocfilehash: 9c3b307668968865b401aedc04c79f95d4f32513
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "91171343"
---
# <a name="-warnaserror-c-compiler-options"></a>-warnaserror (Opciones del compilador de C#)

La opción **-warnaserror+** trata todas las advertencias como errores  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-warnaserror[+ | -][:warning-list]  
```  
  
## <a name="remarks"></a>Observaciones  

 Cualquier mensaje que se notificaría de manera normal como una advertencia se notifica en su lugar como un error, y el proceso de compilación se detiene (no se compila ningún archivo de salida).  
  
 De manera predeterminada, **-warnaserror-** está en vigor, lo que provoca que las advertencias no impidan la generación de un archivo de salida. **-warnaserror**, que es igual que **-warnaserror+**, hace que las advertencias se traten como errores.  
  
 Opcionalmente, si solo quiere que algunas advertencias específicas se traten como errores, puede especificar una lista separada por comas de números de advertencia que se tratarán como errores. Se puede especificar el conjunto de todas las advertencias de nulabilidad con la abreviatura **nullable**.
  
 Use [-warn](./warn-compiler-option.md) para especificar el nivel de advertencias que quiere que muestre el compilador. Use [-nowarn](./nowarn-compiler-option.md) para deshabilitar determinadas advertencias.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1. Abra la página **Propiedades** del proyecto.  
  
2. Haga clic en la página de propiedades de **Compilar**.  
  
3. Modifique la propiedad **Tratar advertencias como errores**.  
  
 Para establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.TreatWarningsAsErrors>.  
  
## <a name="example"></a>Ejemplo  

 Compile `in.cs` y haga que el compilador no muestre ninguna advertencia:  
  
```console  
csc -warnaserror in.cs  
csc -warnaserror:642,649,652,nullable in.cs  
```  
  
## <a name="see-also"></a>Vea también

- [Opciones del compilador de C#](./index.md)
- [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
