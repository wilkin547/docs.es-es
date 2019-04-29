---
title: -libpath
ms.date: 03/10/2018
helpviewer_keywords:
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
ms.openlocfilehash: b7bfcb0f2034145822922126fe61efea8d8ef269
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793931"
---
# <a name="-libpath"></a>-libpath
Especifica la ubicación de los ensamblados que se hace referencia.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-libpath:dirList  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`dirList`|Obligatorio. Lista delimitada por punto y coma de directorios para el compilador buscar en caso de un ensamblado de referencia no se encuentra en el directorio de trabajo actual (el directorio desde el que se invoca el compilador) o el directorio del sistema de common language runtime. Si el nombre del directorio contiene un espacio, escriba el nombre entre comillas ("").|  
  
## <a name="remarks"></a>Comentarios  
 El `-libpath` opción especifica la ubicación de los ensamblados referenciados por la [-referencia](../../../visual-basic/reference/command-line-compiler/reference.md) opción.  
  
 El compilador busca referencias a ensamblados que no presentan la ruta completa en el siguiente orden:  
  
1. Directorio de trabajo actual. Es el directorio desde donde se invoca al compilador.  
  
2. El directorio del sistema de Common Language Runtime.  
  
3. Directorios especificados por `/libpath`.  
  
4. Directorios especificados por la variable de entorno LIB.  
  
 El `-libpath` opción es sumatoria; si se especifica más de una vez se anexa a valores ya existentes.  
  
 Use `-reference` para especificar una referencia de ensamblado.  
  
|Para establecer /libpath en Visual Studio de entorno de desarrollo integrado|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**. <br />2.  Haga clic en la pestaña **Referencias**.<br />3.  Haga clic en el **hacen referencia a las rutas de acceso...**  botón.<br />4.  En el **las rutas de acceso de referencia** diálogo cuadro, escriba el nombre del directorio en el **carpeta:** cuadro.<br />5.  Haga clic en **Agregar carpeta**.|  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `T2.vb` para crear un archivo .exe. El compilador busca en el directorio de trabajo, en el directorio raíz de la unidad C: y en el directorio nuevos ensamblados de la unidad C: de referencias de ensamblado.  
  
```console  
vbc -libpath:c:\;"c:\New Assemblies" -reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Ensamblados de .NET](../../../standard/assembly/index.md)
- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
