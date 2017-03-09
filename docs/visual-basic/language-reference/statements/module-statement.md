---
title: "Module (Instrucci&#243;n) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "Module"
  - "vb.Module"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "clases [Visual Basic], módulos"
  - "declaraciones, módulos"
  - "Module (instrucción)"
  - "módulos"
  - "módulos, clases"
  - "módulos, declarar"
  - "módulos estándar"
ms.assetid: a1243afc-14a5-45df-95d5-51118aeac362
caps.latest.revision: 24
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 24
---
# Module (Instrucci&#243;n)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Declara el nombre de un módulo e introduce la definición de las variables, propiedades, eventos y procedimientos que incluye el módulo.  
  
## Sintaxis  
  
```  
[ <attributelist> ] [ accessmodifier ]  Module name  
    [ statements ]  
End Module  
```  
  
## Elementos  
 `attributelist`  
 Opcional.  Vea [Lista de atributos](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
 `accessmodifier`  
 Opcional.  Puede ser una de las siguientes:  
  
-   [Public](../../../visual-basic/language-reference/modifiers/public.md)  
  
-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
 Vea [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 `name`  
 Obligatorio.  Nombre de este módulo.  Vea [Nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 `statements`  
 Opcional.  Instrucciones que definen las variables, propiedades, eventos, procedimientos y tipos anidados de este módulo.  
  
 `End Module`  
 Termina la definición `Module`.  
  
## Comentarios  
 Una instrucción `Module` define un tipo de referencia disponible en su espacio de nombres.  Un *módulo* \(a veces denominado *módulo estándar*\) es similar a una clase pero con algunas distinciones importantes.  Cada módulo tiene exactamente una instancia y no necesita ser creado ni asignado a una variable.  Los módulos no admiten la herencia ni implementan interfaces.  Tenga en cuenta que un módulo no es un *tipo* en el sentido en que lo son una clase o una estructura; es decir, no puede declarar que un elemento de programación tenga el tipo de datos de un módulo.  
  
 Sólo puede utilizar `Module` en el nivel de espacio de nombres.  Esto significa que el *contexto de la declaración* de un módulo debe ser un archivo de código fuente o espacio de nombres y no puede ser una clase, estructura, módulo, interfaz, procedimiento o bloque.  No puede anidar un módulo dentro de otro módulo ni dentro de cualquier tipo.  Para obtener más información, vea [Contextos de declaración y niveles de acceso predeterminados](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Un módulo tiene el mismo período de duración que el programa.  Dado que sus miembros son todos de tipo `Shared`, también tienen los períodos de duración iguales al del programa.  
  
 De manera predeterminada, el acceso a los módulos es de tipo [Friend](../../../visual-basic/language-reference/modifiers/friend.md).  Puede ajustar sus niveles de acceso con los modificadores de acceso.  Para obtener más información, vea [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 Todos los miembros de un módulo son de forma implícita de tipo `Shared`.  
  
## Clases y módulos  
 Estos elementos tienen muchas similitudes, pero hay también algunas diferencias importantes.  
  
-   **Terminología.** Las versiones anteriores de Visual Basic reconocen dos tipos de módulos: *módulos de clase* \(archivos .cls\) y *módulos estándar* \(archivos .bas\).  En la versión actual se denominan *clases* y *módulos*, respectivamente.  
  
-   **Miembros compartidos.** Se puede controlar si un miembro de una clase es un miembro compartido o de instancia.  
  
-   **Orientación a objetos.** Las clases son orientadas a objetos, pero los módulos no lo son.  Por tanto, sólo se pueden crear instancias como objetos de las clases.  Para obtener más información, vea [Objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
## Reglas  
  
-   **Modificadores.** Todos los miembros de módulo son implícitamente de tipo [Shared](../../../visual-basic/language-reference/modifiers/shared.md).  No puede utilizar la palabra clave `Shared` al declarar un miembro y no puede modificar el estado compartido de ningún miembro.  
  
-   **Herencia.** Un módulo no puede heredar de ningún tipo distinto de <xref:System.Object>, del que heredan todos los módulos.  En particular, un módulo no puede heredar de otro.  
  
     No puede utilizar [Inherits \(Instrucción\)](../../../visual-basic/language-reference/statements/inherits-statement.md) en una definición de módulo, incluso si es para especificar <xref:System.Object>.  
  
-   **Propiedad Default.** No se pueden definir propiedades predeterminadas en un módulo.  Para obtener más información, vea [Default](../../../visual-basic/language-reference/modifiers/default.md).  
  
## Comportamiento  
  
-   **Nivel de acceso.** En un módulo, puede declarar cada miembro con su propio nivel de acceso.  Los miembros de módulo tienen como valor predeterminado acceso de tipo [Public](../../../visual-basic/language-reference/modifiers/public.md), excepto las variables y constantes, que tienen como valor predeterminado acceso de tipo [Private](../../../visual-basic/language-reference/modifiers/private.md).  Cuando un módulo tiene un acceso más restringido que uno de sus miembros, tiene prioridad el nivel de acceso del módulo especificado.  
  
-   **Ámbito.** Los módulos se incluyen en el ámbito de sus espacios de nombres.  
  
     El ámbito de todos los miembros del módulo es el módulo completo.  Observe que en todos los miembros se realiza la *promoción de tipos*, que provoca que su ámbito sea el espacio de nombres que contiene el módulo.  Para obtener más información, vea [Promoción de tipos](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).  
  
-   **Calificación.** Puede tener varios módulos en un proyecto y puede declarar miembros con el mismo nombre en dos o más módulos.  Sin embargo, si la referencia procede del exterior del módulo debe calificar cualquier referencia a dichos miembros con el nombre del módulo adecuado.  Para obtener más información, vea [Referencias a elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
## Ejemplo  
 [!code-vb[VbVbalrStatements#69](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/module-statement_1.vb)]  
  
## Vea también  
 [Class \(Instrucción\)](../../../visual-basic/language-reference/statements/class-statement.md)   
 [Namespace \(Instrucción\)](../../../visual-basic/language-reference/statements/namespace-statement.md)   
 [Structure \(Instrucción\)](../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Interface \(Instrucción\)](../../../visual-basic/language-reference/statements/interface-statement.md)   
 [Property \(Instrucción\)](../../../visual-basic/language-reference/statements/property-statement.md)   
 [Promoción de tipos](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)