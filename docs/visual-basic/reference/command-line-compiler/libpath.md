---
title: -libpath
ms.date: 03/10/2018
helpviewer_keywords:
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
ms.openlocfilehash: dff7e0c3eb696b9b18f4c4e59240a26c1cb9782c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408554"
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
|`dirList`|Obligatorio. Lista delimitada por punto y coma de directorios para que el compilador busque un ensamblado al que se hace referencia si no lo encuentra en el directorio de trabajo actual (el directorio desde el que se invoca al compilador) o en el directorio del sistema de Common Language Runtime. Si el nombre del directorio contiene un espacio, escríbalo entre comillas (" ").|  
  
## <a name="remarks"></a>Comentarios  
 La opción `-libpath` especifica la ubicación de los ensamblados a los que se hace referencia con la opción [-reference](reference.md).  
  
 El compilador busca referencias a ensamblados que no presentan la ruta completa en el siguiente orden:  
  
1. Directorio de trabajo actual. Es el directorio desde donde se invoca al compilador.  
  
2. El directorio del sistema de Common Language Runtime.  
  
3. Directorios especificados por `-libpath`.  
  
4. Directorios especificados por la variable de entorno LIB.  
  
 La opción `-libpath` es sumatoria; si se especifica más de una vez, se anexa a valores ya existentes.  
  
 Use `-reference` para especificar una referencia a un ensamblado.  
  
|Para establecer -libpath en el entorno de desarrollo integrado de Visual Studio|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**. <br />2.  Haga clic en la pestaña **Referencias**.<br />3.  Haga clic en el botón **Rutas de acceso de referencia...** .<br />4.  En el cuadro de diálogo **Rutas de acceso de referencia**, escriba el nombre del directorio en el cuadro **Carpeta:** .<br />5.  Haga clic en **Agregar carpeta**.|  
  
## <a name="example"></a>Ejemplo  
 El código siguiente compila `T2.vb` para crear un archivo. exe. El compilador busca las referencias de ensamblado en el directorio de trabajo, en el directorio raíz de la unidad C:, y en el directorio New Assemblies (Ensamblados nuevos) de la unidad C:.  
  
```console  
vbc -libpath:c:\;"c:\New Assemblies" -reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Ensamblados de .NET](../../../standard/assembly/index.md)
- [Compilador de línea de comandos de Visual Basic](index.md)
- [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
