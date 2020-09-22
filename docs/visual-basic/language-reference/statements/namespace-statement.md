---
title: Namespace (Instrucción)
ms.date: 07/20/2015
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
ms.openlocfilehash: cef339a66458ee9657dc1706082c3c5328746dc6
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875208"
---
# <a name="namespace-statement"></a>Namespace (Instrucción)

Declara el nombre de un espacio de nombres y hace que el código fuente que sigue a la declaración se compile dentro de ese espacio de nombres.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
Namespace [Global.] { name | name.name }  
    [ componenttypes ]  
End Namespace  
```  
  
## <a name="parts"></a>Partes  

 Global  
 Opcional. Permite definir un espacio de nombres fuera del espacio de nombres raíz del proyecto. Vea [espacios de nombres en Visual Basic](../../programming-guide/program-structure/namespaces.md).  
  
 `name`  
 Obligatorio. Nombre único que identifica el espacio de nombres. Debe ser un identificador de Visual Basic válido. Para obtener más información, vea [nombres de elementos declarados](../../programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 `componenttypes`  
 Opcional. Elementos que componen el espacio de nombres. Estos incluyen, entre otros, enumeraciones, estructuras, interfaces, clases, módulos, delegados y otros espacios de nombres.  
  
 `End Namespace`  
 Finaliza un `Namespace` bloque.  
  
## <a name="remarks"></a>Comentarios  

 Los espacios de nombres se usan como sistema de la organización. Proporcionan una manera de clasificar y presentar los elementos de programación que se exponen a otros programas y aplicaciones. Tenga en cuenta que un espacio de nombres no es un *tipo* en el sentido de que una clase o estructura es: no puede declarar un elemento de programación para que tenga el tipo de datos de un espacio de nombres.  
  
 Todos los elementos de programación declarados después de una `Namespace` instrucción pertenecen a ese espacio de nombres. Visual Basic continúa compilando elementos en el último espacio de nombres declarado hasta que encuentra una `End Namespace` instrucción u otra `Namespace` instrucción.  
  
 Si ya hay un espacio de nombres definido, incluso fuera del proyecto, puede agregarle elementos de programación. Para ello, use una `Namespace` instrucción para dirigir Visual Basic para compilar los elementos en ese espacio de nombres.  
  
 Puede usar una `Namespace` instrucción solo en el nivel de archivo o de espacio de nombres. Esto significa que el contexto de la *declaración* de un espacio de nombres debe ser un archivo de código fuente u otro espacio de nombres, y no puede ser una clase, una estructura, un módulo, una interfaz o un procedimiento. Para obtener más información, vea [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).  
  
 Puede declarar un espacio de nombres dentro de otro. No hay ningún límite estricto para los niveles de anidamiento que puede declarar, pero recuerde que cuando otro código tiene acceso a los elementos declarados en el espacio de nombres más interno, debe usar una cadena de calificación que contenga todos los nombres de espacio de nombres de la jerarquía de anidamiento.  
  
## <a name="access-level"></a>Nivel de acceso  

 Los espacios de nombres se tratan como si tienen un `Public` nivel de acceso. Se puede tener acceso a un espacio de nombres desde el código en cualquier parte del mismo proyecto, desde otros proyectos que hagan referencia al proyecto y desde cualquier ensamblado compilado a partir del proyecto.  
  
 Los elementos de programación declarados en el nivel de espacio de nombres, lo que significa que en un espacio de nombres pero no dentro de ningún otro elemento, pueden tener `Public` `Friend` acceso o. Si no se especifica, el nivel de acceso de este elemento utiliza de `Friend` forma predeterminada. Los elementos que se pueden declarar en el nivel de espacio de nombres incluyen clases, estructuras, módulos, interfaces, enumeraciones y delegados. Para obtener más información, vea [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).  
  
## <a name="root-namespace"></a>Espacio de nombres raíz  

 Todos los nombres de espacios de nombres del proyecto se basan en un *espacio de nombres raíz*. Visual Studio asigna el nombre del proyecto como el espacio de nombres raíz predeterminado para todo el código del proyecto. Por ejemplo, si el proyecto se llama `Payroll`, los respectivos elementos de programación pertenecerán al espacio de nombres `Payroll`. Si declara `Namespace funding` , el nombre completo de ese espacio de nombres es `Payroll.funding` .  
  
 Si desea especificar un espacio de nombres existente en una `Namespace` instrucción, como en el ejemplo de clase de lista genérica, puede establecer el espacio de nombres raíz en un valor null. Para ello, haga clic en **propiedades del proyecto** en el menú **proyecto** y, a continuación, desactive la entrada **espacio de nombres raíz** para que el cuadro esté vacío. Si no lo hizo en el ejemplo de clase de lista genérica, el compilador Visual Basic tomaría `System.Collections.Generic` como un nuevo espacio de nombres dentro del proyecto `Payroll` , con el nombre completo de `Payroll.System.Collections.Generic` .  
  
 Como alternativa, puede usar la `Global` palabra clave para hacer referencia a los elementos de los espacios de nombres definidos fuera del proyecto. Esto le permite conservar el nombre del proyecto como espacio de nombres raíz. Esto reduce la posibilidad de combinar accidentalmente los elementos de programación con los de los espacios de nombres existentes. Para obtener más información, vea la sección "palabra clave global en nombres completos" en [espacios de nombres en Visual Basic](../../programming-guide/program-structure/namespaces.md).  
  
 La `Global` palabra clave también se puede utilizar en una instrucción de espacio de nombres. con lo que podrá definir un espacio de nombres fuera del espacio de nombres raíz del proyecto. Para obtener más información, vea la sección "palabra clave global en instrucciones de espacio de nombres" en [espacios de nombres en Visual Basic](../../programming-guide/program-structure/namespaces.md).  
  
 **Solución.** El espacio de nombres raíz puede producir concatenaciones inesperadas de nombres de espacios de nombres. Si hace referencia a los espacios de nombres definidos fuera del proyecto, el compilador de Visual Basic puede interpretarlos como espacios de nombres anidados en el espacio de nombres raíz. En tal caso, el compilador no reconoce ningún tipo que ya se haya definido en los espacios de nombres externos. Para evitar esto, establezca el espacio de nombres raíz en un valor nulo como se describe en "espacio de nombres de la raíz" o use la `Global` palabra clave para obtener acceso a los elementos de los espacios de nombres externos.  
  
## <a name="attributes-and-modifiers"></a>Atributos y modificadores  

 No se pueden aplicar atributos a un espacio de nombres. Un atributo contribuye a la información en los metadatos del ensamblado, lo que no es significativo para los clasificadores de origen, como los espacios de nombres.  
  
 No se puede aplicar ningún modificador de acceso o procedimiento, ni ningún otro modificador, a un espacio de nombres. Dado que no es un tipo, estos modificadores no son significativos.  
  
## <a name="example"></a>Ejemplo  

 En el siguiente ejemplo se declaran dos espacios de nombres, uno anidado en el otro.  
  
 [!code-vb[VbVbalrStatements#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#43)]  
  
## <a name="example"></a>Ejemplo  

 En el siguiente ejemplo se declaran varios espacios de nombres anidados en una sola línea y es equivalente al ejemplo anterior.  
  
 [!code-vb[VbVbalrStatements#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#41)]  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se obtiene acceso a la clase definida en los ejemplos anteriores.  
  
 [!code-vb[VbVbalrStatements#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#42)]  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se define el esqueleto de una nueva clase de lista genérica y se agrega al <xref:System.Collections.Generic?displayProperty=nameWithType> espacio de nombres.  
  
```vb  
Namespace System.Collections.Generic  
    Class specialSortedList(Of T)  
        Inherits List(Of T)  
        ' Insert code to define the special generic list class.  
    End Class  
End Namespace  
```  
  
## <a name="see-also"></a>Consulte también

- [Instrucción Imports (Tipo y espacio de nombres de .NET)](imports-statement-net-namespace-and-type.md)
- [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md)
- [Espacios de nombres en Visual Basic](../../programming-guide/program-structure/namespaces.md)
