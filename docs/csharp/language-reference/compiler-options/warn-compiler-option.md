---
description: -warn (Opciones del compilador de C#)
title: -warn (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /warn
helpviewer_keywords:
- warning level [C#]
- /w compiler option [C#]
- -w compiler option [C#]
- -warn compiler option [C#]
- /warn compiler option [C#]
- w compiler option [C#]
- warn compiler option [C#]
ms.custom: updateeachrelease
ms.assetid: 5f80ff59-4991-4382-9f9a-77da18446e71
ms.openlocfilehash: d59274423e6f9844d3ab22f3ac513ba1a05d7f07
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "91171356"
---
# <a name="-warn-c-compiler-options"></a>-warn (Opciones del compilador de C#)

La opción **-warn** especifica el nivel de advertencia que debe mostrar el compilador.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-warn:option  
```  
  
## <a name="arguments"></a>Argumentos  

 `option`  
 El nivel de advertencia que quiere que se muestre para la compilación: los números más bajos muestran solo advertencias de gravedad alta; los números más altos muestran más advertencias. El valor debe ser cero o un entero positivo:

|Nivel de advertencia|Significado|
|-------------------|-------------|
|0|Desactiva la emisión de todos los mensajes de advertencia.|
|1|Muestra mensajes de advertencia graves.|  
|2|Muestra advertencias de nivel 1 además de determinadas advertencias menos graves, como advertencias sobre ocultar miembros de clase.|  
|3|Muestra advertencias de nivel 2 además de determinadas advertencias menos graves, como advertencias sobre expresiones que siempre se evalúan como `true` o `false`.|  
|4 (el valor predeterminado)|Muestra todas las advertencias de nivel 3 además de advertencias informativas.|
|5|Muestra las advertencias de nivel 4, además de [advertencias adicionales](https://github.com/dotnet/roslyn/blob/a6013f3213c902c0973b2d371c3007217d610533/docs/compilers/CSharp/Warnversion%20Warning%20Waves.md) del compilador incluido con C# 9.0.|
|Mayor que 5|Cualquier valor mayor que 5 se tratará como 5. Normalmente, se proporciona un valor grande arbitrario (por ejemplo, `9999`) para asegurarse de que siempre reciba todas las advertencias si el compilador se actualiza con nuevos niveles de advertencia.|
  
## <a name="remarks"></a>Observaciones  

 Para obtener información sobre un error o advertencia, puede buscar el código de error en el Índice de la Ayuda. Para conocer otras maneras de obtener información sobre un error o advertencia, vea [Errores del compilador de C#](../compiler-messages/index.md).  
  
 Use [-warnaserror](./warnaserror-compiler-option.md) para tratar todas las advertencias como errores. Use [-nowarn](./nowarn-compiler-option.md) para deshabilitar determinadas advertencias.  
  
 **-w** es la forma abreviada de **-warn**.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1. Abra la página **Propiedades** del proyecto.  
  
2. Haga clic en la página de propiedades de **Compilar**.  
  
3. Modifique la propiedad de **Nivel de advertencia**.  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.WarningLevel%2A>.  
  
## <a name="example"></a>Ejemplo  

 Compile `in.cs` y haga que el compilador solo muestre advertencias de nivel 1:  
  
```console  
csc -warn:1 in.cs  
```  
  
## <a name="see-also"></a>Vea también

- [Opciones del compilador de C#](./index.md)
- [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)
