---
title: -addmodule
ms.date: 03/09/2018
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
ms.openlocfilehash: 2db122acc03056a9cb6f355119d4c4e6da6ed175
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91097792"
---
# <a name="-addmodule"></a>-addmodule

Hace que el compilador facilite al proyecto que se está compilando toda la información de tipos presente en los archivos especificados.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-addmodule:fileList  
```  
  
## <a name="arguments"></a>Argumentos  

 `fileList`  
 Obligatorio. Lista delimitada por comas de archivos que contienen metadatos, pero que no contienen manifiestos de ensamblado. Los nombres de archivo que contienen espacios deben ir entre comillas (" ").  
  
## <a name="remarks"></a>Comentarios  

 Los archivos mostrados con el parámetro `fileList` se deben crear con la opción `-target:module` o con otro equivalente del compilador para `-target:module`.  
  
 Todos los módulos agregados con `-addmodule` deben encontrarse en el mismo directorio que el archivo de salida en tiempo de ejecución. Es decir, se puede especificar un módulo de cualquier directorio en el tiempo de compilación, pero el módulo debe encontrarse en el directorio de la aplicación en tiempo de ejecución. Si no es así, obtendrá un error <xref:System.TypeLoadException>.  
  
 Si especifica (implícita o explícitamente) cualquier opción [-target (Visual Basic)](target.md) que no sea `-target:module` con `-addmodule`, los archivos que pase a `-addmodule` se convertirán en parte del ensamblado del proyecto. Se requiere un ensamblado para ejecutar un archivo de salida que tenga uno o más archivos agregados con `-addmodule`.  
  
 Use [-reference (Visual Basic)](reference.md) para importar metadatos de un archivo que contenga un ensamblado.  
  
> [!NOTE]
> La opción `-addmodule` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  

 En el código siguiente se crea un módulo.  
  
 [!code-vb[VbVbalrCompiler#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#47)]  
  
 En el código siguiente se importan los tipos del módulo.  
  
 [!code-vb[VbVbalrCompiler#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#48)]  
  
 Al ejecutar `t1`, genera `802`.  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](index.md)
- [-target (Visual Basic)](target.md)
- [-reference (Visual Basic)](reference.md)
- [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
