---
title: Namespace (Instrucción)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Namespace
helpviewer_keywords:
- namespaces [Visual Basic], root
- Namespace statement [Visual Basic]
- namespaces [Visual Basic], nested
- declaring namespaces [Visual Basic], syntax
- namespaces [Visual Basic], declaring
- root namespaces
- declarations [Visual Basic], namespaces
ms.assetid: a31fbd95-9ace-4c3d-bbb1-51222a2272b2
caps.latest.revision: 39
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 90eb33bdbc01afc983869c919f9d7b2feab44037
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="namespace-statement"></a>Namespace (Instrucción)
Declara el nombre de un espacio de nombres y hace que el código fuente que sigue a la declaración se compile dentro de ese espacio de nombres.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Namespace [Global.] { name | name.name }  
    [ componenttypes ]  
End Namespace  
```  
  
## <a name="parts"></a>Elementos  
 Global  
 Opcional. Le permite definir un espacio de nombres del espacio de nombres raíz del proyecto. Vea [espacios de nombres en Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).  
  
 `name`  
 Requerido. Un nombre único que identifica el espacio de nombres. Debe ser un identificador válido de Visual Basic. Para obtener más información, consulte [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 `componenttypes`  
 Opcional. Elementos que componen el espacio de nombres. Estos incluyen, pero no se limitan a, enumeraciones, estructuras, interfaces, clases, módulos, delegados y otros espacios de nombres.  
  
 `End Namespace`  
 Finaliza un `Namespace` bloque.  
  
## <a name="remarks"></a>Comentarios  
 Espacios de nombres se utilizan como un sistema de la organización. Proporcionan una manera de clasificar y presentar elementos de programación que se exponen a otros programas y aplicaciones. Tenga en cuenta que un espacio de nombres no es un *tipo* en el sentido de que es una clase o estructura, no puede declarar un elemento de programación que el tipo de datos de un espacio de nombres.  
  
 Todos los elementos de programación declaran después un `Namespace` instrucción pertenecen a ese espacio de nombres. Visual Basic continúa compilar elementos en el último espacio de nombres declarado hasta que encuentra, ya sea un `End Namespace` instrucción u otro `Namespace` instrucción.  
  
 Si ya está definido un espacio de nombres, incluso fuera del proyecto, puede agregar elementos de programación a él. Para ello, use un `Namespace` instrucción para indicar a Visual Basic para compilar elementos en ese espacio de nombres.  
  
 Puede usar un `Namespace` instrucción en el nivel de archivo o espacio de nombres. Esto significa que la *contexto de la declaración* para un espacio de nombres debe ser un archivo de origen o de otro espacio de nombres y no puede ser una clase, estructura, módulo, interfaz o procedimiento. Para obtener más información, vea [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).  
  
 Puede declarar un espacio de nombres dentro de otra. No hay ningún límite estricto en los niveles de anidamiento puede declarar, pero recuerde que cuando otro código tiene acceso a los elementos declarados en el espacio de nombres más interno, debe usar una cadena de calificación que contiene todos los nombres de espacio de nombres en la jerarquía de anidamiento.  
  
## <a name="access-level"></a>Nivel de acceso  
 Espacios de nombres se tratan como si tuvieran un `Public` nivel de acceso. Puede tener acceso a un espacio de nombres desde el código en cualquier lugar en el mismo proyecto, desde otros proyectos que hagan referencia al proyecto y de cualquier ensamblado compilado a partir del proyecto.  
  
 Pueden tener elementos de programación que se declara en el nivel de espacio de nombres, lo que significa que en un espacio de nombres pero no dentro de cualquier otro elemento, `Public` o `Friend` acceso. Si no se especifica, utiliza el nivel de acceso de como un elemento `Friend` de forma predeterminada. Elementos que se pueden declarar en el nivel de espacio de nombres incluyen clases, estructuras, módulos, interfaces, enumeraciones y delegados. Para obtener más información, vea [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).  
  
## <a name="root-namespace"></a>Namespace de raíz  
 Todos los nombres de espacio de nombres en el proyecto se basan en un *espacio de nombres raíz*. Visual Studio asigna el nombre del proyecto como el espacio de nombres raíz predeterminado para todo el código del proyecto. Por ejemplo, si el proyecto se llama `Payroll`, los respectivos elementos de programación pertenecerán al espacio de nombres `Payroll`. Si declara `Namespace funding`, el nombre completo de ese espacio de nombres es `Payroll.funding`.  
  
 Si desea especificar un espacio de nombres existente en una `Namespace` instrucción, como en el ejemplo de clase de lista genérica, puede establecer el espacio de nombres raíz en un valor null. Para ello, haga clic en **propiedades del proyecto** desde el **proyecto** menú y, a continuación, desactive la **espacio de nombres raíz** entrada para que el cuadro está vacío. Si no lo en el ejemplo de la clase de lista genérica, el compilador de Visual Basic tardaría `System.Collections.Generic` como un nuevo espacio de nombres en el proyecto `Payroll`, con el nombre completo del `Payroll.System.Collections.Generic`.  
  
 Como alternativa, puede usar el `Global` palabra clave para hacer referencia a los elementos de espacios de nombres definidos fuera del proyecto. Esto le permite conservar el nombre del proyecto como el espacio de nombres raíz. Esto reduce la posibilidad de combinar involuntariamente los elementos de programación junto con los espacios de nombres existentes. Para obtener más información, vea la sección "Global palabra clave en nombres completos" en [espacios de nombres en Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).  
  
 El `Global` palabra clave puede utilizarse en una instrucción Namespace. con lo que podrá definir un espacio de nombres fuera del espacio de nombres raíz del proyecto. Para obtener más información, vea la sección "Instrucciones de palabra clave Global en Namespace" en [espacios de nombres en Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md).  
  
 **Solución de problemas.** El espacio de nombres raíz puede provocar concatenaciones inesperadas de espacios de nombres. Si hace referencia a espacios de nombres definidos fuera del proyecto, el compilador de Visual Basic puede generarlos como espacios de nombres anidados en el espacio de nombres raíz. En tal caso, el compilador no reconoce los tipos que ya se han definido en los espacios de nombres externos. Para evitar esto, establezca el espacio de nombres raíz en un valor nulo como se describe en "Namespace raíz", o utilice el `Global` palabra clave para acceder a los elementos de espacios de nombres externos.  
  
## <a name="attributes-and-modifiers"></a>Los atributos y modificadores  
 No se puede aplicar atributos a un espacio de nombres. Un atributo proporciona información a los metadatos del ensamblado, que no son significativos para los clasificadores de origen como los espacios de nombres.  
  
 No se puede aplicar cualquier tipo de acceso o modificadores del procedimiento o cualquier otro modificador a un espacio de nombres. Dado que no es un tipo, estos modificadores no son significativos.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se declara dos espacios de nombres, uno anidado en el otro.  
  
 [!code-vb[VbVbalrStatements#43](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/namespace-statement_1.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se declara varios espacios de nombres anidados en una sola línea y es equivalente al ejemplo anterior.  
  
 [!code-vb[VbVbalrStatements#41](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/namespace-statement_2.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se obtiene acceso a la clase definida en los ejemplos anteriores.  
  
 [!code-vb[VbVbalrStatements#42](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/namespace-statement_3.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se define el esqueleto de una nueva clase de lista genérica y lo agrega a la <xref:System.Collections.Generic?displayProperty=nameWithType> espacio de nombres.  
  
```vb  
Namespace System.Collections.Generic  
    Class specialSortedList(Of T)  
        Inherits List(Of T)  
        ' Insert code to define the special generic list class.  
    End Class  
End Namespace  
```  
  
## <a name="see-also"></a>Vea también  
 [Imports (instrucción), espacio de nombres y tipo .NET](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)  
 [Nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [Espacios de nombres en Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)
