---
description: 'Más información sobre: compilación condicional en Visual Basic'
title: Compilación condicional
ms.date: 07/20/2015
helpviewer_keywords:
- conditional compilation [Visual Basic], about conditional compilation
- compilation [Visual Basic], conditional
ms.assetid: 9c35e55e-7eee-44fb-a586-dad1f1884848
ms.openlocfilehash: e9cb8a5af4dfbf2ffadef8edd8f6583614188391
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100476142"
---
# <a name="conditional-compilation-in-visual-basic"></a>Compilación condicional en Visual Basic

En la *compilación condicional*, determinados bloques de código de un programa se compilan de forma selectiva mientras que otros se omiten.  
  
 Por ejemplo, puede que desee escribir instrucciones de depuración que comparen la velocidad de los distintos enfoques para la misma tarea de programación, o puede que desee localizar una aplicación para varios idiomas. Las instrucciones de compilación condicional están diseñadas para ejecutarse durante el tiempo de compilación, no en tiempo de ejecución.  
  
 Se denotan los bloques de código que se van a compilar condicionalmente con la `#If...Then...#Else` Directiva. Por ejemplo, para crear versiones en francés y en alemán de la misma aplicación desde el mismo código fuente, se insertan segmentos de código específicos de la plataforma en las `#If...Then` instrucciones usando las constantes predefinidas `FrenchVersion` y `GermanVersion` . En el ejemplo siguiente se muestra cómo:  
  
 [!code-vb[VbVbalrConditionalComp#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#5)]  
  
 Si establece el valor de la `FrenchVersion` constante de compilación condicional en `True` en tiempo de compilación, se compila el código condicional de la versión en francés. Si establece el valor de la `GermanVersion` constante en `True` , el compilador usa la versión en alemán. Si no se establece ninguno en `True` , se ejecuta el código del último `Else` bloque.  
  
> [!NOTE]
> La finalización automática no funcionará al editar código y utilizar directivas de compilación condicional si el código no forma parte de la rama actual.  
  
## <a name="declaring-conditional-compilation-constants"></a>Declarar constantes de compilación condicional  

 Puede establecer constantes de compilación condicional de una de estas tres maneras:  
  
- En el **Diseñador de proyectos**  
  
- En la línea de comandos cuando se usa el compilador de línea de comandos  
  
- En el código  
  
 Las constantes de compilación condicional tienen un ámbito especial y no se puede tener acceso a ellas desde el código estándar. El ámbito de una constante de compilación condicional depende de la forma en que se establece. En la tabla siguiente se muestra el ámbito de las constantes declaradas con cada una de las tres maneras mencionadas anteriormente.  
  
|Cómo se establece Constant|Ámbito de Constant|  
|---|---|  
|**Diseñador de proyectos**|Público a todos los archivos del proyecto|  
|Línea de comandos|Público a todos los archivos pasados al compilador de línea de comandos|  
|`#Const` instrucción en el código|Privado del archivo en el que se declara|  
  
|Para establecer constantes en el diseñador de proyectos|  
|---|  
|-Antes de crear el archivo ejecutable, establezca las constantes en el **Diseñador de proyectos** siguiendo los pasos que se indican en [Administración de propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties).|  
  
|Para establecer constantes en la línea de comandos|  
|---|  
|-Use el modificador **-d** para especificar constantes de compilación condicional, como en el ejemplo siguiente:<br />     `vbc MyProj.vb /d:conFrenchVersion=–1:conANSI=0`<br />     No se requiere espacio entre el modificador **-d** y la primera constante. Para obtener más información, vea [-define (Visual Basic)](../../reference/command-line-compiler/define.md).<br />     Las declaraciones de línea de comandos invalidan las declaraciones especificadas en el **Diseñador de proyectos**, pero no las borran. Los argumentos establecidos en el **Diseñador de proyectos** permanecen en vigor para las compilaciones posteriores.<br />     Al escribir constantes en el propio código, no hay ninguna regla estricta en cuanto a su ubicación, ya que su ámbito es todo el módulo en el que se declaran.|  
  
|Para establecer constantes en el código|  
|---|  
|-Coloque las constantes en el bloque de declaración del módulo en el que se usan. Esto ayuda a mantener el código organizado y más fácil de leer.|  
  
## <a name="related-topics"></a>Temas relacionados  
  
|Title|Descripción|  
|---|---|  
|[Convenciones de código y estructura de programas](program-structure-and-code-conventions.md)|Proporciona sugerencias para facilitar la lectura y el mantenimiento del código.|  
  
## <a name="reference"></a>Referencia  

 [#Const (directiva)](../../language-reference/directives/const-directive.md)  
  
 [#If...Then...#Else (directivas)](../../language-reference/directives/if-then-else-directives.md)  
  
 [-define (Visual Basic)](../../reference/command-line-compiler/define.md)
