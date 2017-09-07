---
title: -out (Opciones del compilador de C#)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /out
dev_langs:
- CSharp
helpviewer_keywords:
- /out compiler option [C#]
- out compiler option [C#]
- -out compiler option [C#]
ms.assetid: 70d91d01-7bd2-4aea-ba8b-4e9807e9caa5
caps.latest.revision: 15
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: a6db728bc98f5223fc35268a1cce41021ff530cc
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="out-c-compiler-options"></a>/out (Opciones del compilador de C#)
La opción **/out** especifica el nombre del archivo de salida.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
/out:filename  
```  
  
## <a name="arguments"></a>Argumentos  
 `filename`  
 El nombre del archivo de salida creado por el compilador.  
  
## <a name="remarks"></a>Comentarios  
 En la línea de comandos, es posible especificar varios archivos de salida de una compilación. El compilador espera encontrar al menos un archivo de código fuente después de la opción **/out**. Posteriormente, todos los archivos de código fuente se compilarán en el archivo de salida especificado por la opción **/out**.  
  
 Hay que especificar el nombre completo y la extensión del archivo que se quiere crear.  
  
 Si no se especifica el nombre del archivo de salida:  
  
-   Un archivo .exe toma el nombre del archivo de código fuente que contiene el método **Main**.  
  
-   Un archivo .dll o .netmodule toma el nombre del primer archivo de código fuente.  
  
 Un archivo de código fuente usado para compilar un archivo de salida no puede usarse para compilar otro archivo de este tipo en la misma compilación.  
  
 Cuando se producen varios archivos de salida en una compilación de línea de comandos, recuerde que solo uno de los archivos de salida puede ser un ensamblado y que solo el primero que haya especificado (ya sea implícita o explícitamente con **/out**) puede ser el ensamblado.  
  
 Todos los módulos que se produzcan como parte de una compilación se convierten en archivos asociados a cualquier ensamblado que también se haya producido en la compilación. Use [ildasm.exe](https://msdn.microsoft.com/library/f7dy01k1) para ver el manifiesto del ensamblado y los archivos asociados.  
  
 Es obligatorio usar la opción /out del compilador para que un archivo exe sea el destino de un ensamblado de confianza. Para obtener más información, vea [Ensamblados de confianza](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra la página **Propiedades** del proyecto.  
  
2.  Haga clic en la página de propiedades **Aplicación**.  
  
3.  Modifique la propiedad **Nombre del ensamblado**.  
  
     Para establecer esta opción del compilador mediante programación: <xref:VSLangProj80.ProjectProperties3.OutputFileName%2A> es una propiedad de solo lectura que se determina a partir de una combinación del tipo de proyecto (ejecutable, biblioteca, etc.) y el nombre del ensamblado. Es necesario modificar una de estas propiedades o ambas para establecer el nombre del archivo de salida.  
  
## <a name="example"></a>Ejemplo  
 Compile `t.cs` y cree el archivo de salida `t.exe`, así como compile `t2.cs` y cree el archivo de salida del módulo `mymodule.netmodule`:  
  
```console  
csc t.cs /out:mymodule.netmodule /target:module t2.cs  
```  
  
## <a name="see-also"></a>Vea también  
 [Opciones del compilador de C#](../../../csharp/language-reference/compiler-options/index.md)   
 [Ensamblados de confianza](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055)   
 [Administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties)

