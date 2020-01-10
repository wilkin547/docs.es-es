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
ms.openlocfilehash: 5035466de4aa17c374824e1b0f02ed594731a9d3
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75716808"
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
|`symbol`|Obligatoria. Símbolo que se va a definir.|  
|`value`|Opcional. Valor que se va a asignar a `symbol`. Si `value` es una cadena, debe estar rodeada por secuencias de barras diagonales inversas (\\") en lugar de Comillas. Si no se especifica ningún valor, se considera como verdadero.|  
  
## <a name="remarks"></a>Notas  
 La opción `-define` tiene un efecto similar al uso de una directiva de preprocesador de `#Const` en el archivo de código fuente, con la excepción de que las constantes definidas con `-define` son públicas y se aplican a todos los archivos del proyecto.  
  
 Los símbolos creados por esta opción se pueden usar con la directiva `#If`...`Then`...`#Else` para compilar archivos de origen condicionalmente.  
  
 `-d` es la forma abreviada de `-define`.  
  
 Se pueden definir varios símbolos con `-define`; use una coma para separar las definiciones de símbolos.  
  
|Para establecer-definir en el entorno de desarrollo integrado de Visual Studio|  
|---|  
|1. tener un proyecto seleccionado en **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**. <br />2. Haga clic en la pestaña **compilar** .<br />3. Haga clic en **avanzadas**.<br />4. modifique el valor en el cuadro **constantes personalizadas** .|  
  
## <a name="example"></a>Ejemplo  
 En el siguiente código se definen y usan dos constantes de compilador condicionales.  
  
 [!code-vb[VbVbalrCompiler#45](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCompiler/VB/Class1.vb#45)]  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [#If...Then...#Else (directivas)](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [#Const (directiva)](../../../visual-basic/language-reference/directives/const-directive.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
