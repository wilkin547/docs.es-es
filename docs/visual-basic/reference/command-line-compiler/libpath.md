---
title: -libpath
ms.date: 03/10/2018
helpviewer_keywords:
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
ms.openlocfilehash: 8f4e415576562885c9edbd3d2dddbe2a271e9923
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005468"
---
# <a name="-libpath"></a>-libpath
Especifica la ubicación de los ensamblados a los que se hace referencia.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-libpath:dirList  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`dirList`|Obligatorio. Lista de directorios delimitados por punto y coma para que el compilador busque si un ensamblado al que se hace referencia no se encuentra en el directorio de trabajo actual (el directorio desde el que se invoca al compilador) o en el directorio del sistema del Common Language Runtime. Si el nombre del directorio contiene un espacio, incluya el nombre entre comillas ("").|  
  
## <a name="remarks"></a>Comentarios  
 La opción `-libpath` especifica la ubicación de los ensamblados a los que hace referencia la opción [-Reference](../../../visual-basic/reference/command-line-compiler/reference.md) .  
  
 El compilador busca referencias a ensamblados que no presentan la ruta completa en el siguiente orden:  
  
1. Directorio de trabajo actual. Es el directorio desde donde se invoca al compilador.  
  
2. El directorio del sistema de Common Language Runtime.  
  
3. Directorios especificados por `/libpath`.  
  
4. Directorios especificados por la variable de entorno LIB.  
  
 La opción `-libpath` es aditiva; Si se especifica más de una vez, se anexa a los valores anteriores.  
  
 Use `-reference` para especificar una referencia de ensamblado.  
  
|Para establecer/LIBPATH en el entorno de desarrollo integrado de Visual Studio|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**. <br />2.  Haga clic en la pestaña **Referencias**.<br />3.  Haga clic en el botón rutas de acceso de **referencia...** .<br />4.  En el cuadro de diálogo rutas de acceso de **referencia** , escriba el nombre del directorio en el cuadro **carpeta:** .<br />5.  Haga clic en **Agregar carpeta**.|  
  
## <a name="example"></a>Ejemplo  
 El código siguiente compila `T2.vb` para crear un archivo. exe. El compilador busca en el directorio de trabajo, en el directorio raíz de la unidad C:, y en el directorio New assemblies de la unidad C: para las referencias de ensamblado.  
  
```console  
vbc -libpath:c:\;"c:\New Assemblies" -reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Ensamblados de .NET](../../../standard/assembly/index.md)
- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
