---
title: -addmodule
ms.date: 03/09/2018
helpviewer_keywords:
- /addmodule compiler option [Visual Basic]
- addmodule compiler option [Visual Basic]
- -addmodule compiler option [Visual Basic]
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
ms.openlocfilehash: 5a6d367f4b09de600bb744aa2abed0da2c93aa0b
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/01/2019
ms.locfileid: "57202371"
---
# <a name="-addmodule"></a>-addmodule
Hace que el compilador facilite al proyecto que se está compilando toda la información de tipos presente en los archivos especificados.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-addmodule:fileList  
```  
  
## <a name="arguments"></a>Argumentos  
 `fileList`  
 Obligatorio. Lista delimitada por comas de los archivos que contienen metadatos pero no contienen manifiestos de ensamblado. Los nombres de archivo que contienen espacios deben ir entre comillas ("").  
  
## <a name="remarks"></a>Comentarios  
 Los archivos mostrados por la `fileList` parámetro debe crearse con el `-target:module` opción, o con el equivalente de otro compilador a `-target:module`.  
  
 Todos los módulos agregados mediante `-addmodule` debe estar en el mismo directorio que el archivo de salida en tiempo de ejecución. Es decir, puede especificar un módulo en cualquier directorio en tiempo de compilación, pero el módulo debe estar en el directorio de la aplicación en tiempo de ejecución. Si no es así, obtendrá un <xref:System.TypeLoadException> error.  
  
 Si especifica (implícita o explícitamente) cualquier[-destino (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md) opción distinto `-target:module` con `-addmodule`, los archivos que pase a `-addmodule` pasan formar parte del ensamblado del proyecto. Se requiere un ensamblado para ejecutar un archivo de salida que tiene uno o más archivos agregados con `-addmodule`.  
  
 Use [/Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md) para importar metadatos de un archivo que contiene un ensamblado.  
  
> [!NOTE]
>  El `-addmodule` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible solo cuando se compila desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  
 El código siguiente crea un módulo.  
  
 [!code-vb[VbVbalrCompiler#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#47)]  
  
 El código siguiente importa los tipos del módulo.  
  
 [!code-vb[VbVbalrCompiler#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/OptionStrictOff.vb#48)]  
  
 Al ejecutar `t1`, lo que da como resultado `802`.  
  
## <a name="see-also"></a>Vea también
- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [-referencia (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
