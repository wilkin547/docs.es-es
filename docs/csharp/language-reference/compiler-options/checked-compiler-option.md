---
title: -checked (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /checked
helpviewer_keywords:
- checked compiler option [C#]
- -checked compiler option [C#]
- /checked compiler option [C#]
ms.assetid: fb7475d3-e6a6-4e6d-b86c-69e7a74c854b
ms.openlocfilehash: cb4dbadfa4efd0750ffd3dea88a3f661e2f85a8e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173775"
---
# <a name="-checked-c-compiler-options"></a>-checked (Opciones del compilador de C#)
La opción **-checked** especifica si una instrucción aritmética de enteros que produce un valor fuera del intervalo del tipo de datos y que no está en el ámbito de las palabras clave [checked](../keywords/checked.md) o [unchecked](../keywords/unchecked.md) provocará una excepción en tiempo de ejecución.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-checked[+ | -]  
```  
  
## <a name="remarks"></a>Comentarios  
 Una instrucción aritmética de enteros que está en el ámbito de la palabra clave `checked` o `unchecked` no está sujeta al efecto de la opción **-checked**.  
  
 Si una instrucción aritmética de enteros que no está en el ámbito de la palabra clave `checked` o `unchecked` produce un valor fuera del intervalo del tipo de datos, y si se usa **-checked+** (o **-checked**) en la compilación, la instrucción provoca una excepción en tiempo de ejecución. Si se usa **-checked-** en la compilación, la instrucción no produce una excepción en tiempo de ejecución.  
  
 El valor predeterminado para esta opción es **-checked-** y la comprobación de desbordamiento está deshabilitada.

 A veces, las herramientas automatizadas que se usan para compilar aplicaciones de gran tamaño establecen -check en +. Una situación para usar -checked- es reemplazar el valor predeterminado global de la herramienta especificando -checked-.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1. Abra la página **Propiedades** del proyecto. Para obtener más información, consulte [Compilar (Página, Diseñador de proyectos) (C#)](/visualstudio/ide/reference/build-page-project-designer-csharp).  
  
2. Haga clic en la página de propiedades de **Compilar**.  
  
3. Haga clic en el botón **Avanzada** .  
  
4. Modifique la propiedad **Comprobar el desbordamiento aritmético**.  
  
 Para acceder a esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.CheckForOverflowUnderflow%2A>.  
  
## <a name="example"></a>Ejemplo  
 El comando siguiente compila `t2.cs`. El uso de `-checked` en el comando especifica que cualquier instrucción de aritmética de enteros del archivo que no esté en el ámbito de la palabra clave `checked` o `unchecked` y que produzca un valor fuera del intervalo del tipo de datos provocará una excepción en tiempo de ejecución.  
  
```console  
csc t2.cs -checked  
```  
  
## <a name="see-also"></a>Vea también

- [Opciones del compilador de C#](./index.md)
- [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
