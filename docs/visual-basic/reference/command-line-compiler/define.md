---
title: -define
ms.date: 03/10/2018
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
ms.openlocfilehash: fd0875f09bf3ba7211ede500aa0da45f8b7cd2c7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344764"
---
# <a name="-define-visual-basic"></a>-define (Visual Basic)
Permite definir constantes condicionales para el compilador.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-define:["]symbol[=value][,symbol[=value]]["]  
```

o

```console  
-d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|de esquema JSON|  
|---|---|  
|`symbol`|Requerido. Símbolo que se va a definir.|  
|`value`|Opcional. Valor que se va a asignar a `symbol`. If `value` is a string, it must be surrounded by backslash/quotation-mark sequences (\\") instead of quotation marks. Si no se especifica ningún valor, se considera como verdadero.|  
  
## <a name="remarks"></a>Comentarios  
 The `-define` option has an effect similar to using a `#Const` preprocessor directive in your source file, except that constants defined with `-define` are public and apply to all files in the project.  
  
 Los símbolos creados por esta opción se pueden usar con la directiva `#If`...`Then`...`#Else` para compilar archivos de origen condicionalmente.  
  
 `-d` es la forma abreviada de `-define`.  
  
 Se pueden definir varios símbolos con `-define`; use una coma para separar las definiciones de símbolos.  
  
|Para definir/establecer en el entorno de desarrollo integrado de Visual Studio|  
|---|  
|1.  Have a project selected in **Solution Explorer**. En el menú **Proyecto**, haga clic en **Propiedades**. <br />2.  Click the **Compile** tab.<br />3.  Click **Advanced**.<br />4.  Modify the value in the **Custom Constants** box.|  
  
## <a name="example"></a>Ejemplo  
 En el siguiente código se definen y usan dos constantes de compilador condicionales.  
  
 [!code-vb[VbVbalrCompiler#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#45)]  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [#If...Then...#Else (directivas)](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [#Const (directiva)](../../../visual-basic/language-reference/directives/const-directive.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
