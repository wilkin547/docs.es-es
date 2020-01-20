---
title: 'Constructores estáticos: Guía de programación de C#'
ms.date: 07/20/2015
helpviewer_keywords:
- static constructors [C#]
- constructors [C#], static
ms.assetid: 151ec95e-3c4d-4ed7-885d-95b7a3be2e7d
ms.openlocfilehash: 7b8171e75bbd27a1079f2c6cc1b7aef6400d7419
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2020
ms.locfileid: "76115761"
---
# <a name="static-constructors-c-programming-guide"></a>Constructores estáticos (Guía de programación de C#)
Un constructor estático se usa para inicializar cualquier dato [estático](../../language-reference/keywords/static.md) o realizar una acción determinada que solo debe realizarse una vez. Es llamado automáticamente antes de crear la primera instancia o de hacer referencia a cualquier miembro estático.  
  
 [!code-csharp[csProgGuideObjects#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#14)]  
 
## <a name="remarks"></a>Comentarios
Los constructores estáticos tienen las propiedades siguientes:  
  
- Un constructor estático no permite modificadores de acceso ni tiene parámetros.  

- Una clase o struct solo puede tener un constructor estático.

- Los constructores estáticos no se pueden heredar ni sobrecargar.

- No se puede llamar a un constructor estático directamente y solo está pensado para que Common Language Runtime (CLR) lo llame. Se invoca automáticamente.

- El usuario no puede controlar cuándo se ejecuta el constructor estático en el programa.
  
- Se le llama automáticamente para inicializar la [clase](../../language-reference/keywords/class.md) antes de crear la primera instancia o de hacer referencia a cualquier miembro estático. Un constructor estático se ejecutará antes que un constructor de instancia. Se llama al constructor estático de un tipo cuando se invoca un método estático asignado a un evento o un delegado y no cuando este se asigna. Si los inicializadores de variable del campo estático están presentes en la clase o el constructor estático, se ejecutarán en el orden textual en el que aparecen en la declaración de clase inmediatamente anterior a la ejecución del constructor estático.

- Si no proporciona un constructor estático para inicializar los campos estáticos, todos los campos estáticos se inicializan en su valor predeterminado como se muestra en [Valores predeterminados de los tipos de C#](../../language-reference/builtin-types/default-values.md).
  
- Si un constructor estático inicia una excepción, el motor en tiempo de ejecución no lo invocará una segunda vez y el tipo seguirá sin inicializar durante el período de duración del dominio de aplicación donde se ejecuta el programa. Normalmente, se inicia una excepción <xref:System.TypeInitializationException> cuando un constructor estático no puede crear una instancia de un tipo o para una excepción no controlada que se produce dentro de un constructor estático. En el caso de los constructores estáticos implícitos no definidos de forma explícita en el código fuente, la solución de problemas puede requerir la inspección del código de lenguaje intermedio (IL).

- La presencia de un constructor estático evita la adición del atributo de tipo <xref:System.Reflection.TypeAttributes.BeforeFieldInit>. Esto limita la optimización en tiempo de ejecución.

- Un campo declarado como `static readonly` solo se puede asignar como parte de su declaración o en un constructor estático. Si no se necesita un constructor estático explícito, inicialice campos estáticos en la declaración, en lugar de a través de un constructor estático para una mejor optimización en tiempo de ejecución.

> [!Note]
> Aunque no es directamente accesible, la presencia de un constructor estático explícito debe documentarse para ayudar con la solución de problemas de excepciones de inicialización.

### <a name="usage"></a>Uso

- Los constructores estáticos se usan normalmente cuando la clase hace uso de un archivo de registro y el constructor escribe entradas en dicho archivo.  
- Los constructores estáticos también son útiles al crear clases contenedoras para código no administrado, cuando el constructor puede llamar al método `LoadLibrary`.  

- Los constructores estáticos también son un lugar adecuado para aplicar comprobaciones en tiempo de ejecución en el parámetro de tipo que no se puede comprobar en tiempo de compilación a través de restricciones (restricciones de parámetro de tipo).

## <a name="example"></a>Ejemplo
 En este ejemplo, la clase `Bus` tiene un constructor estático. Cuando se crea la primera instancia de `Bus` (`bus1`), se invoca el constructor estático para inicializar la clase. En el resultado del ejemplo, se comprueba que el constructor estático se ejecuta solo una vez, incluso si se crean dos instancias de `Bus`, y que se ejecuta antes de que se ejecute el constructor de instancia.  
  
 [!code-csharp[csProgGuideObjects#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#15)]
 
## <a name="c-language-specification"></a>Especificación del lenguaje C#
Para obtener más información, consulte la sección sobre [constructores estáticos](~/_csharplang/spec/classes.md#static-constructors) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).
  
## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Clases y structs](./index.md)
- [Constructores](./constructors.md)
- [Clases estáticas y sus miembros](./static-classes-and-static-class-members.md)
- [Finalizadores](./destructors.md)
- [Instrucciones de diseño de constructores](../../../standard/design-guidelines/constructor.md#type-constructor-guidelines)
- [Advertencia de seguridad - CA2121: Los constructores estáticos deben ser privados](https://docs.microsoft.com/visualstudio/code-quality/ca2121-static-constructors-should-be-private)
