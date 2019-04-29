---
title: Compilación condicional en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- conditional compilation [Visual Basic], about conditional compilation
- compilation [Visual Basic], conditional
ms.assetid: 9c35e55e-7eee-44fb-a586-dad1f1884848
ms.openlocfilehash: 828edf2e5491394f5ac802b5c9babfb3df359e59
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61758462"
---
# <a name="conditional-compilation-in-visual-basic"></a>Compilación condicional en Visual Basic
En *compilación condicional*, bloques concretos de código en un programa se compilan selectivamente mientras otros se omiten.  
  
 Por ejemplo, puede escribir instrucciones de depuración que comparan la velocidad de enfoques diferentes para la tarea de programación misma, o que desee localizar una aplicación para varios idiomas. Instrucciones de compilación condicional están diseñadas para ejecutarse durante el tiempo de compilación, no en tiempo de ejecución.  
  
 Para indicar los bloques de código que se compilarán con la `#If...Then...#Else` directiva. Por ejemplo, para francés y alemán de crear versiones de la misma aplicación desde el mismo código fuente, incrustar los segmentos de código específico de plataforma en `#If...Then` instrucciones mediante las constantes predefinidas `FrenchVersion` y `GermanVersion`. En el ejemplo siguiente se muestra cómo:  
  
 [!code-vb[VbVbalrConditionalComp#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConditionalComp/VB/Class1.vb#5)]  
  
 Si establece el valor de la `FrenchVersion` constante de compilación condicional para `True` en tiempo de compilación, se compila el código condicional de la versión en francés. Si establece el valor de la `GermanVersion` constante a `True`, el compilador usa la versión en alemán. Si ninguno está establecido en `True`, el código en los últimos `Else` bloquear ejecuciones.  
  
> [!NOTE]
>  Autocompletar le no funcionará al editar código y el uso de directivas de compilación condicional si el código no forma parte de la rama actual.  
  
## <a name="declaring-conditional-compilation-constants"></a>Declarar constantes de compilación condicional  
 Puede establecer las constantes de compilación condicional en uno de tres maneras:  
  
- En el **Diseñador de proyectos**  
  
- En la línea de comandos cuando se usa el compilador de línea de comandos  
  
- En el código  
  
 Constantes de compilación condicional tienen un ámbito especial y no es accesible desde el código estándar. El ámbito de una constante de compilación condicional es dependiente de la forma en que se establece. La tabla siguiente enumera el ámbito de las constantes declaradas con cada uno de los tres métodos mencionados anteriormente.  
  
|¿Cómo se establece (constante)|Ámbito de constante|  
|---|---|  
|**Diseñador de proyectos**|Public para todos los archivos del proyecto|  
|Línea de comandos|Public para todos los archivos que se pasó al compilador de línea de comandos|  
|`#Const` instrucción de código|En el archivo en el que se declara private|  
  
|Para definir constantes en el Diseñador de proyectos|  
|---|  
|-Antes de crear el archivo ejecutable, defina las constantes en el **Diseñador de proyectos** siguiendo los pasos proporcionados en [administrar propiedades de soluciones y proyectos](/visualstudio/ide/managing-project-and-solution-properties).|  
  
|Para definir constantes en la línea de comandos|  
|---|  
|-Use el **/d** conmutador para especificar constantes de compilación condicional, como en el ejemplo siguiente:<br />     `vbc MyProj.vb /d:conFrenchVersion=–1:conANSI=0`<br />     No se requiere ningún espacio entre el **/d** modificador y la primera constante. Para obtener más información, consulte [/ define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md).<br />     Las declaraciones de línea de comandos reemplazan a las especificadas en el **Diseñador de proyectos**, pero no eliminarlas. Argumentos que se establecen **Diseñador de proyectos** siguen en vigor para las compilaciones posteriores.<br />     Al escribir constantes en el propio código, no hay ninguna reglas estrictas en cuanto a su ubicación, ya que su ámbito es el módulo completo en el que se declaran.|  
  
|Para definir constantes en el código|  
|---|  
|-Coloque las constantes en el bloque de declaración del módulo en el que se usan. Esto ayuda a mantener el código organizado y más fácil de leer.|  
  
## <a name="related-topics"></a>Temas relacionados  
  
|Título|Descripción|  
|---|---|  
|[Convenciones de código y estructura de programas](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)|Proporciona sugerencias para hacer que el código sea fácil de leer y mantener.|  
  
## <a name="reference"></a>Referencia  
 [#Const (directiva)](../../../visual-basic/language-reference/directives/const-directive.md)  
  
 [#If...Then...#Else (directivas)](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
  
 [/define (Visual Basic)](../../../visual-basic/reference/command-line-compiler/define.md)
