---
title: /debug (Opciones del compilador de C#) | Microsoft Docs
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /debug
dev_langs:
- CSharp
helpviewer_keywords:
- debug compiler option [C#]
- -debug compiler option [C#]
- /debug compiler option [C#]
ms.assetid: e2b48c07-01bc-45cc-a52c-92e9085eb969
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: 6f22f998e4d652075e594c113026dfae18792ded
ms.contentlocale: es-es
ms.lasthandoff: 05/10/2017

---
# <a name="debug-c-compiler-options"></a>/debug (Opciones del compilador de C#)
La opción **/debug** da lugar a que el compilador genere información de depuración y la incluya en el archivo o los archivos de salida.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/debug[+ | -]  
/debug:{full | pdbonly}  
```  
  
## <a name="arguments"></a>Argumentos  
 `+` &#124; `-`  
 Si se especifica `+`, o simplemente **/debug**, el compilador genera información de depuración y la incluye en una base de datos de programa (archivo .pdb). Si se especifica `-`, que es la opción predeterminada si no especifica **/debug**, no se crea información de depuración.  
  
 `full` &#124; `pdbonly`  
 Especifica el tipo de información de depuración generado por el compilador. El argumento full, que es la opción predeterminada si no especifica **/debug:pdbonly**, permite asociar un depurador al programa que se ejecuta. Al especificar la opción pdbonly, se permite depurar el código fuente cuando se inicia el programa en el depurador, pero solo muestra el ensamblador cuando el programa que se ejecuta está asociado al depurador.  
  
## <a name="remarks"></a>Comentarios  
 Use esta opción para crear versiones de depuración. Si no se especifica **/debug**, **/debug+** o **/debug:full**, no podrá depurar el archivo de salida del programa.  
  
 Si usa **/debug:full**, sea consciente de que se producirá algún impacto en la velocidad y el tamaño del código optimizado JIT y un pequeño impacto en la calidad del código con **/debug:full**. Recomendamos **/debug:pdbonly** o ningún PDB para generar el código de la versión de lanzamiento.  
  
> [!NOTE]
>  Una diferencia entre **/debug:pdbonly** y **/debug:full** es que con **/debug:full** el compilador emite <xref:System.Diagnostics.DebuggableAttribute>, que se usa para indicar al compilador JIT que la información de depuración está disponible. Por consiguiente, aparecerá un error si el código contiene <xref:System.Diagnostics.DebuggableAttribute> establecido en false si usa **/debug:full**.  
  
 Para obtener más información sobre cómo configurar el rendimiento de depuración de una aplicación, vea [Facilitar la depuración de una imagen](../../../framework/debug-trace-profile/making-an-image-easier-to-debug.md).  
  
 Para cambiar la ubicación del archivo .pdb, vea [/pdb (Opciones del compilador de C#)](../../../csharp/language-reference/compiler-options/pdb-compiler-option.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra la página **Propiedades** del proyecto.  
  
2.  Haga clic en la página de propiedades de **Compilar**.  
  
3.  Haga clic en el botón **Avanzada** .  
  
4.  Modifique la propiedad **Información de depuración**.  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.CSharpProjectConfigurationProperties3.DebugSymbols%2A>.  
  
## <a name="example"></a>Ejemplo  
 Incluir información de depuración en el archivo de salida `app.pdb`:  
  
```  
csc /debug /pdb:app.pdb test.cs  
```  
  
## <a name="see-also"></a>Vea también  
 [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)   
 [NO ESTÁ EN LA COMPILACIÓN Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)
