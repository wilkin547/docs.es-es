---
title: -out (Opciones del compilador de C#)
ms.date: 07/20/2015
f1_keywords:
- /out
helpviewer_keywords:
- /out compiler option [C#]
- out compiler option [C#]
- -out compiler option [C#]
ms.assetid: 70d91d01-7bd2-4aea-ba8b-4e9807e9caa5
ms.openlocfilehash: 6c8408c0c613e361dae0c1db19f854e9421ca467
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "70970377"
---
# <a name="-out-c-compiler-options"></a>-out (Opciones del compilador de C#)
La opción **-out** especifica el nombre del archivo de salida.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-out:filename  
```  
  
## <a name="arguments"></a>Argumentos  
 `filename`  
 El nombre del archivo de salida creado por el compilador.  
  
## <a name="remarks"></a>Comentarios  
 En la línea de comandos, es posible especificar varios archivos de salida de una compilación. El compilador espera encontrar al menos un archivo de código fuente después de la opción **-out**. Posteriormente, todos los archivos de código fuente se compilarán en el archivo de salida especificado por la opción **-out**.  
  
 Hay que especificar el nombre completo y la extensión del archivo que se quiere crear.  
  
 Si no se especifica el nombre del archivo de salida:  
  
- Un archivo .exe toma el nombre del archivo de código fuente que contiene el método **Main**.  
  
- Un archivo .dll o .netmodule toma el nombre del primer archivo de código fuente.  
  
 Un archivo de código fuente usado para compilar un archivo de salida no puede usarse para compilar otro archivo de este tipo en la misma compilación.  
  
 Cuando se producen varios archivos de salida en una compilación de línea de comandos, recuerde que solo uno de los archivos de salida puede ser un ensamblado y que solo el primero que haya especificado (ya sea implícita o explícitamente con **-out**) puede ser el ensamblado.  
  
 Todos los módulos que se produzcan como parte de una compilación se convierten en archivos asociados a cualquier ensamblado que también se haya producido en la compilación. Use [ildasm.exe](../../../framework/tools/ildasm-exe-il-disassembler.md) para ver el manifiesto del ensamblado y los archivos asociados.  
  
 Es obligatorio usar la opción -out del compilador para que un archivo exe sea el destino de un ensamblado de confianza. Para obtener más información, vea [Ensamblados de confianza](../../../standard/assembly/friend.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1. Abra la página **Propiedades** del proyecto.  
  
2. Haga clic en la página de propiedades **Aplicación**.  
  
3. Modifique la propiedad **Nombre del ensamblado**.  
  
     Para establecer esta opción del compilador mediante programación: <xref:VSLangProj80.ProjectProperties3.OutputFileName%2A> es una propiedad de solo lectura que se determina a partir de una combinación del tipo de proyecto (ejecutable, biblioteca, etc.) y el nombre del ensamblado. Es necesario modificar una de estas propiedades o ambas para establecer el nombre del archivo de salida.  
  
## <a name="example"></a>Ejemplo  
 Compile `t.cs` y cree el archivo de salida `t.exe`, así como compile `t2.cs` y cree el archivo de salida del módulo `mymodule.netmodule`:  
  
```console  
csc t.cs -out:mymodule.netmodule -target:module t2.cs  
```  
  
## <a name="see-also"></a>Vea también

- [Opciones del compilador de C#](./index.md)
- [Ensamblados de confianza](../../../standard/assembly/friend.md)
- [Administrar propiedades de proyectos y de soluciones](/visualstudio/ide/managing-project-and-solution-properties)
