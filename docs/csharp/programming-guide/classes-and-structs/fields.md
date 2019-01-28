---
title: 'Campos: Guía de programación de C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- fields [C#]
ms.assetid: 3cbb2f61-75f8-4cce-b4ef-f5d1b3de0db7
ms.openlocfilehash: ac825940897df3a0f6105a6d9cca8e16cf69eb25
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54655678"
---
# <a name="fields-c-programming-guide"></a>Campos (Guía de programación de C#)
Un *campo* es una variable de cualquier tipo que se declara directamente en una [clase](../../../csharp/language-reference/keywords/class.md) o [struct](../../../csharp/language-reference/keywords/struct.md). Los campos son *miembros* de su tipo contenedor.  
  
 Una clase o struct puede tener campos de instancia o campos estáticos, o ambos. Los campos de instancia son específicos de una instancia de un tipo. Si tiene una clase T, con un campo de instancia F, puede crear dos objetos de tipo T y modificar el valor de F en cada objeto sin afectar el valor del otro objeto. Por el contrario, un campo estático pertenece a la propia clase y se comparte entre todas las instancias de esa clase. Los cambios realizados desde la instancia A serán visibles inmediatamente para las instancias B y C, si tienen acceso al campo.  
  
 Por lo general, solo se deben usar campos para las variables que tienen accesibilidad privada o protegida. Los datos que la clase expone al código de cliente deben proporcionarse a través de [métodos](../../../csharp/programming-guide/classes-and-structs/methods.md), [propiedades](../../../csharp/programming-guide/classes-and-structs/properties.md) e [indizadores](../../../csharp/programming-guide/indexers/index.md). Mediante estas construcciones para el acceso indirecto a los campos internos, se puede proteger de los valores de entrada no válidos. Un campo privado que almacena los datos expuestos por una propiedad pública se denomina *memoria auxiliar* o *campo de respaldo*.  
  
 Los campos almacenan habitualmente los datos que deben ser accesibles para más de un método de clase y que deben almacenarse durante más tiempo de lo que dura un único método. Por ejemplo, es posible que una clase que representa una fecha de calendario tenga tres campos enteros: uno para el mes, otro para el día y otro para el año. Las variables que no se usan fuera del ámbito de un único método se deben declarar como *variables locales* dentro del campo del método.  
  
 Los campos se declaran en el bloque de clase especificando el nivel de acceso del campo, seguido por el tipo del campo, seguido por el nombre del campo. Por ejemplo:  
  
 [!code-csharp[csProgGuideObjects#61](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/fields_1.cs)]  
  
 Para obtener acceso a un campo en un objeto, agregue un punto después del nombre de objeto, seguido del nombre del campo, como en `objectname.fieldname`. Por ejemplo:  
  
 [!code-csharp[csProgGuideObjects#62](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/fields_2.cs)]  
  
 Se puede proporcionar un valor inicial a un campo mediante el operador de asignación cuando se declara el campo. Para asignar automáticamente el campo `day` a `"Monday"`, por ejemplo, se declararía `day` como en el ejemplo siguiente:  
  
 [!code-csharp[csProgGuideObjects#63](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/fields_3.cs)]  
  
 Los campos se inicializan inmediatamente antes de que se llame al constructor para la instancia del objeto. Si el constructor asigna el valor de un campo, sobrescribirá cualquier valor dado durante la declaración del campo. Para obtener más información, vea [Using Constructors](../../../csharp/programming-guide/classes-and-structs/using-constructors.md) (Uso de constructores).  
  
> [!NOTE]
>  Un inicializador de campo no puede hacer referencia a otros campos de instancia.  
  
 Se pueden marcar campos como [público](../../../csharp/language-reference/keywords/public.md), [privado](../../../csharp/language-reference/keywords/private.md), [protegido](../../../csharp/language-reference/keywords/protected.md), [interno](../../../csharp/language-reference/keywords/internal.md), [protegido interno](../../../csharp/language-reference/keywords/protected-internal.md) o [privado protegido](../../../csharp/language-reference/keywords/private-protected.md). Estos modificadores de acceso definen cómo los usuarios de la clase pueden obtener acceso a los campos. Para obtener más información, consulte [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).  
  
 Opcionalmente, un campo se puede declarar como [static](../../../csharp/language-reference/keywords/static.md). Esto hace que el campo esté disponible para los llamadores en cualquier momento, aunque no exista ninguna instancia de la clase. Para más información, vea [Clases estáticas y sus miembros](../../../csharp/programming-guide/classes-and-structs/static-classes-and-static-class-members.md).  
  
 Se puede declarar un campo como [readonly](../../../csharp/language-reference/keywords/readonly.md). Solamente se puede asignar un valor a un campo de solo lectura durante la inicialización o en un constructor. Un campo `static readonly` es muy similar a una constante, salvo que el compilador de C# no tiene acceso al valor de un campo estático de solo lectura en tiempo de compilación, solo en tiempo de ejecución. Para obtener más información, vea [Constants](../../../csharp/programming-guide/classes-and-structs/constants.md) (Constantes).  
  
## <a name="c-language-specification"></a>Especificación del lenguaje C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../../../csharp/programming-guide/index.md)
- [Clases y structs](../../../csharp/programming-guide/classes-and-structs/index.md)
- [Utilizar constructores](../../../csharp/programming-guide/classes-and-structs/using-constructors.md)
- [Herencia](../../../csharp/programming-guide/classes-and-structs/inheritance.md)
- [Modificadores de acceso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)
- [Clases y miembros de clase abstractos y sellados](../../../csharp/programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md)
