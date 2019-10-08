---
title: -addmodule
ms.date: 03/09/2018
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
ms.openlocfilehash: fbe3634d1fbc03acd56ef7276d65fd54493b9806
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72002421"
---
# <a name="-addmodule"></a>-addmodule
Hace que el compilador facilite al proyecto que se está compilando toda la información de tipos presente en los archivos especificados.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-addmodule:fileList  
```  
  
## <a name="arguments"></a>Argumentos  
 `fileList`  
 Obligatorio. Lista delimitada por comas de archivos que contienen metadatos, pero que no contienen manifiestos de ensamblado. Los nombres de archivo que contienen espacios deben ir entre comillas ("").  
  
## <a name="remarks"></a>Comentarios  
 Los archivos enumerados por el parámetro `fileList` deben crearse con la opción `-target:module` o con otro equivalente del compilador a `-target:module`.  
  
 Todos los módulos agregados con `-addmodule` deben estar en el mismo directorio que el archivo de salida en tiempo de ejecución. Es decir, puede especificar un módulo en cualquier directorio en tiempo de compilación, pero el módulo debe estar en el directorio de la aplicación en tiempo de ejecución. Si no es así, obtendrá un error <xref:System.TypeLoadException>.  
  
 Si especifica (implícita o explícitamente) una opción[de destino (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) distinta de `-target:module` con `-addmodule`, los archivos que pase a `-addmodule` pasarán a formar parte del ensamblado del proyecto. Se requiere un ensamblado para ejecutar un archivo de salida que tiene uno o más archivos agregados con `-addmodule`.  
  
 Use [/Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) para importar metadatos de un archivo que contenga un ensamblado.  
  
> [!NOTE]
> La opción `-addmodule` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible al compilar desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  
 En el código siguiente se crea un módulo.  
  
 [!code-vb[VbVbalrCompiler#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#47)]  
  
 En el código siguiente se importan los tipos del módulo.  
  
 [!code-vb[VbVbalrCompiler#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#48)]  
  
 Al ejecutar `t1`, genera `802`.  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [-Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
