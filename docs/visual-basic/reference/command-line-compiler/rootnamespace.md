---
title: -rootnamespace
ms.date: 03/13/2018
f1_keywords:
- /rootnamespace
- rootnamespace
helpviewer_keywords:
- /rootnamespace compiler option [Visual Basic]
- -rootnamespace compiler option [Visual Basic]
- rootnamespace compiler option [Visual Basic]
ms.assetid: e9245edf-6bef-420d-a7c7-324117752783
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 13bce09ca9fd1ae9ebb919a9245d8ccf87fbde1d
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/18/2018
ms.locfileid: "46002611"
---
# <a name="-rootnamespace"></a>-rootnamespace
Especifica un espacio de nombres para todas las declaraciones de tipos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-rootnamespace:namespace  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|de esquema JSON|  
|---|---|  
|`namespace`|El nombre del espacio de nombres en el que se va a incluir todas las declaraciones de tipo para el proyecto actual.|  
  
## <a name="remarks"></a>Comentarios  
 Si usa el archivo ejecutable de Visual Studio (Devenv.exe) para compilar un proyecto creado en el entorno de desarrollo integrado de Visual Studio, use `-rootnamespace` para especificar el valor de la <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> propiedad. Consulte [modificadores de línea de comandos para Devenv](/visualstudio/ide/reference/devenv-command-line-switches) para obtener más información.  
  
 Utilizar el Desensamblador de MSIL de common language runtime (`Ildasm.exe`) para ver los nombres de espacio de nombres en el archivo de salida.  
  
|Para establecer - rootnamespace en el entorno de desarrollo integrado de Visual Studio|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**. <br />2.  Haga clic en la pestaña **Aplicación** .<br />3.  Modifique el valor en el **raíz Namespace** cuadro.|  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `In.vb` y engloba todas las declaraciones de tipo en el espacio de nombres `mynamespace`.  
  
```console
vbc -rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
- [Ildasm.exe (Desensamblador de IL)](../../../framework/tools/ildasm-exe-il-disassembler.md)  
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
