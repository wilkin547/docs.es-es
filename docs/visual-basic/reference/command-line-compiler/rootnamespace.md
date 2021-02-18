---
description: Más información sobre -rootnamespace
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
ms.openlocfilehash: 0e034999a65bf5294e63c8f9cec1a4ce4de39a4b
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100474088"
---
# <a name="-rootnamespace"></a>-rootnamespace

Especifica un espacio de nombres para todas las declaraciones de tipos.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-rootnamespace:namespace  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`namespace`|Nombre del espacio de nombres en el que se van a incluir todas las declaraciones de tipos para el proyecto actual.|  
  
## <a name="remarks"></a>Comentarios  

 Si usa el archivo ejecutable de Visual Studio (devenv.exe) para compilar un proyecto creado en el entorno de desarrollo integrado de Visual Studio, utilice `-rootnamespace` para especificar el valor de la propiedad <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A>. Para obtener más información, vea [Modificadores de línea de comandos para Devenv](/visualstudio/ide/reference/devenv-command-line-switches).  
  
 Use el desensamblador de MSIL de Common Language Runtime (`Ildasm.exe`) para ver los nombres de los espacios de nombres en el archivo de salida.  
  
|Para establecer -rootnamespace en el entorno de desarrollo integrado de Visual Studio|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**. <br />2.  Haga clic en la pestaña **Aplicación** .<br />3.  Modifique el valor del cuadro **Espacio de nombres raíz**.|  
  
## <a name="example"></a>Ejemplo  

 El código siguiente compila `In.vb` y agrega todas las declaraciones de tipos en el espacio de nombres `mynamespace`.  
  
```console
vbc -rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](index.md)
- [Ildasm.exe (Desensamblador de IL)](../../../framework/tools/ildasm-exe-il-disassembler.md)
- [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
