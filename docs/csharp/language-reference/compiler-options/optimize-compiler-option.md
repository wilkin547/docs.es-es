---
title: -optimize (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /optimize
helpviewer_keywords:
- /optimize compiler option [C#]
- -o compiler option [C#]
- optimize compiler option [C#]
- /o compiler option [C#]
- -optimize compiler option [C#]
- compiler optimization [C#]
- o compiler option [C#]
ms.assetid: 6dd5b6f2-cd1d-4593-a9f4-1c2ed9404ca0
ms.openlocfilehash: 86c8ebb2d2061085be4c00e8ac95448e1c341161
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33212467"
---
# <a name="-optimize-c-compiler-options"></a>-optimize (Opciones del compilador de C#)
La opción **-optimize** habilita o deshabilita las optimizaciones realizadas por el compilador para que el archivo de salida sea menor, más rápido y más eficaz.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-optimize[+ | -]  
```  
  
## <a name="remarks"></a>Comentarios  
 **-optimize** también indica a Common Language Runtime que optimice el código en tiempo de ejecución.  
  
 De forma predeterminada, las optimizaciones están deshabilitadas. Especifique **-optimize+** para habilitar las optimizaciones.  
  
 Al compilar un módulo para que lo use un ensamblado, use la misma configuración de **-optimize** que la del ensamblado.  
  
 **-o** es la forma abreviada de **-optimize**.  
  
 Es posible combinar las opciones **-optimize** y [-debug](../../../csharp/language-reference/compiler-options/debug-compiler-option.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra la página **Propiedades** del proyecto.  
  
2.  Haga clic en la página de propiedades de **Compilar**.  
  
3.  Modifique la propiedad **Optimizar código**.  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.Optimize%2A>.  
  
## <a name="example"></a>Ejemplo  
 Compile `t2.cs` y habilite las optimizaciones del compilador:  
  
```console  
csc t2.cs -optimize  
```  
  
## <a name="see-also"></a>Vea también  
 [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)  
 [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
