---
title: -imports
ms.date: 03/10/2018
helpviewer_keywords:
- /imports compiler option [Visual Basic]
- imports compiler option [Visual Basic]
- -imports compiler option [Visual Basic]
ms.assetid: 9a93fb53-c080-497b-bf9b-441022dbbc39
ms.openlocfilehash: 2a1dd19189ff65413255b9bc137e1a7f0227bbe1
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716646"
---
# <a name="-imports-visual-basic"></a>-Imports (Visual Basic)
Importa los espacios de nombres de un ensamblado especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-imports:namespaceList  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|de esquema JSON|  
|---|---|  
|`namespaceList`|Obligatoria. Lista delimitada por comas de los espacios de nombres que se van a importar.|  
  
## <a name="remarks"></a>Notas  
 La opción `-imports` importa cualquier espacio de nombres definido en el conjunto actual de archivos de código fuente o desde cualquier ensamblado al que se hace referencia.  
  
 Los miembros de un espacio de nombres especificado con `-imports` están disponibles para todos los archivos de código fuente de la compilación. Use la [instrucción Imports (espacio de nombres y tipo de .net)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) para usar un espacio de nombres en un solo archivo de código fuente.  
  
|Para establecer las importaciones en el entorno de desarrollo integrado de Visual Studio|  
|---|  
|1. tener un proyecto seleccionado en **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**. <br />2. Haga clic en la pestaña **referencias** .<br />3. Escriba el nombre del espacio de nombres en el cuadro situado junto al botón **Agregar importación de usuario** .<br />4. Haga clic en el botón **Agregar importación de usuario** .|  
  
## <a name="example"></a>Ejemplo  
 El siguiente código se compila cuando se especifica `-imports:system.globalization`. Sin él, la compilación correcta requiere que una instrucción `Imports System.Globalization` esté incluida al principio del archivo de código fuente, o que la propiedad esté completa como `System.Globalization.CultureInfo.CurrentCulture.Name`.

```vb
Module Example
   Public Sub Main()
      Console.WriteLine($"The current culture is {CultureInfo.CurrentCulture.Name}")
   End Sub
End Module
```

## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Referencias y la instrucción Imports](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
