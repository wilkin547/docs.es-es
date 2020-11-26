---
title: Mejorar la depuración con los atributos de visualización del depurador
description: Introducción a los atributos de presentación del depurador en .NET, que permiten al desarrollador de tipos especificar también el aspecto que tendrá el tipo cuando se muestre en un depurador.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- debugger, display attributes
- DebuggerTypeProxyAttribute attribute
- debugging [.NET Framework], debugger display attributes
- DebuggerDisplayAttribute attribute
- display attributes for debugger
- DebuggerBrowsableAttribute attribute
ms.assetid: 72bb7aa9-459b-42c4-9163-9312fab4c410
ms.openlocfilehash: 2e556358490409a0fa7b345c4454eb43cf607e32
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96244371"
---
# <a name="enhancing-debugging-with-the-debugger-display-attributes"></a>Mejorar la depuración con los atributos de visualización del depurador

Los atributos de visualización del depurador permiten al desarrollador del tipo, que especifica y mejor comprende el comportamiento del runtime de ese tipo, que especifique también el aspecto que tendrá ese tipo cuando se muestre en un depurador. Además, los atributos de visualización del depurador que proporcionan una propiedad `Target` pueden aplicarse en el nivel de ensamblado por usuarios sin conocimiento del código fuente. El atributo <xref:System.Diagnostics.DebuggerDisplayAttribute> controla la forma en que se muestra un tipo o un miembro en las ventanas de variables del depurador. El atributo <xref:System.Diagnostics.DebuggerBrowsableAttribute> determina si un campo o propiedad se muestra en las ventanas de variables del depurador y cómo se muestra. El atributo <xref:System.Diagnostics.DebuggerTypeProxyAttribute> especifica un tipo sustitutivo, o un proxy, para un tipo y cambia la forma en que se muestra el tipo en las ventanas del depurador. Cuando se ve una variable que tiene un proxy, o un tipo sustitutivo, el proxy reemplaza al tipo original en la ventana de presentación del depurador. En la ventana de las variables del depurador se muestran sólo los miembros públicos del tipo de servidor proxy. No se muestran los miembros privados.  
  
## <a name="using-the-debuggerdisplayattribute"></a>Usar el atributo DebuggerDisplayAttribute  

El constructor <xref:System.Diagnostics.DebuggerDisplayAttribute.%23ctor%2A> tiene un argumento único: una cadena que se va a mostrar en la columna de valor de las instancias del tipo. Esta cadena puede contener llaves ({ y }). El texto encerrado entre llaves se evalúa como una expresión. Por ejemplo, el código de C# siguiente hace que "Recuento = 4" se muestre cuando el signo más (+) está seleccionado para expandir la presentación del depurador para una instancia de `MyHashtable`.  

```csharp
[DebuggerDisplay("Count = {count}")]
class MyHashtable
{
    public int count = 4;
}
```

Los atributos que se aplican en las propiedades a las que se hace referencia en la expresión no se procesan. Para el compilador de C#, se permite una expresión general que solo tenga acceso implícito a esta referencia para la instancia actual del tipo de destino. La expresión está limitada; no tiene acceso a los alias, variables locales ni punteros. En el código de C#, puede usar una expresión general entre las llaves que tenga acceso implícito al puntero `this` solo para la instancia actual del tipo de destino.

Por ejemplo, si un objeto de C# tiene un `ToString()` invalidado, el depurador llamará a la invalidación y mostrará su resultado en lugar del `{<typeName>}.` estándar. Por lo tanto, si ha invalidado `ToString()`, no necesita usar <xref:System.Diagnostics.DebuggerDisplayAttribute>. Si utiliza ambos, el atributo <xref:System.Diagnostics.DebuggerDisplayAttribute> tiene prioridad sobre el reemplazo de `ToString()`.

## <a name="using-the-debuggerbrowsableattribute"></a>Usar el atributo DebuggerBrowsableAttribute

 Aplique <xref:System.Diagnostics.DebuggerBrowsableAttribute> en un campo o propiedad para especificar cómo va a mostrarse el campo o la propiedad en la ventana del depurador. El constructor de este atributo toma uno de los valores de enumeración <xref:System.Diagnostics.DebuggerBrowsableState>, que especifica uno de los estados siguientes:

- <xref:System.Diagnostics.DebuggerBrowsableState.Never> indica que el miembro no se muestra en la ventana de datos.  Por ejemplo, con este valor para <xref:System.Diagnostics.DebuggerBrowsableAttribute> en un campo se quita el campo de la jerarquía; el campo no se muestra cuando expande el tipo envolvente haciendo clic en el signo más (+) para la instancia del tipo.

- <xref:System.Diagnostics.DebuggerBrowsableState.Collapsed> indica que el miembro se muestra pero no se expande de manera predeterminada.  Este es el comportamiento predeterminado.

- <xref:System.Diagnostics.DebuggerBrowsableState.RootHidden> indica que el propio miembro no se muestra, pero sus objetos constituyentes se muestran si es una matriz o una colección.

> [!NOTE]
> <xref:System.Diagnostics.DebuggerBrowsableAttribute> no es compatible con Visual Basic en la versión 2.0 de .NET Framework.

En el siguiente ejemplo de código se muestra el uso de <xref:System.Diagnostics.DebuggerBrowsableAttribute> para evitar que la propiedad que lo sigue aparezca en la ventana del depurador para la clase.

```csharp
[DebuggerBrowsable(DebuggerBrowsableState.Never)]
public static string y = "Test String";
```

## <a name="using-the-debuggertypeproxy"></a>Usar DebuggerTypeProxy

 Use el atributo <xref:System.Diagnostics.DebuggerTypeProxyAttribute> cuando necesite realizar cambios significativos y fundamentales en la vista de depuración de un tipo, sin cambiar el propio tipo. El atributo <xref:System.Diagnostics.DebuggerTypeProxyAttribute> se usa para especificar un servidor proxy de presentación de un tipo y permitir a un desarrollador que ajuste la vista para el tipo.  Este atributo, como <xref:System.Diagnostics.DebuggerDisplayAttribute>, también se puede usar en el nivel de ensamblado, en cuyo caso la propiedad <xref:System.Diagnostics.DebuggerTypeProxyAttribute.Target%2A> especifica el tipo para el que se usará el servidor proxy. El uso recomendado es que este atributo especifique un tipo anidado privado que aparece dentro del tipo al que se aplica el atributo.  Un evaluador de expresiones que admite los visores de tipo comprueba la existencia de este atributo cuando se muestra un tipo. Si se encuentra el atributo, el evaluador de expresiones sustituye el tipo de servidor proxy de presentación por el tipo al que se aplica el atributo.

 Cuando está presente <xref:System.Diagnostics.DebuggerTypeProxyAttribute>, en la ventana de las variables del depurador se muestran solo los miembros públicos del tipo de servidor proxy. No se muestran los miembros privados. El comportamiento de la ventana de datos no lo modifican las vistas mejoradas por atributos.

 Para evitar disminuciones innecesarias del rendimiento, los atributos del servidor proxy de presentación no se procesan hasta que el objeto esté expandido, ya sea a través del usuario que hace clic en el signo más (+) situado junto al tipo en una ventana de datos o a través de la aplicación del atributo <xref:System.Diagnostics.DebuggerBrowsableAttribute>. Por consiguiente, se recomienda no aplicar ningún atributo al tipo de presentación. Los atributos pueden y deben aplicarse en el cuerpo del tipo de presentación.

 En el ejemplo de código siguiente se muestra el uso del atributo <xref:System.Diagnostics.DebuggerTypeProxyAttribute> para especificar un tipo que se va a usar como servidor proxy de presentación del depurador.

```csharp
[DebuggerTypeProxy(typeof(HashtableDebugView))]
class MyHashtable : Hashtable
{
    private const string TestString =
        "This should not appear in the debug window.";

    internal class HashtableDebugView
    {
        private Hashtable hashtable;
        public const string TestStringProxy =
            "This should appear in the debug window.";

        // The constructor for the type proxy class must have a
        // constructor that takes the target type as a parameter.
        public HashtableDebugView(Hashtable hashtable)
        {
            this.hashtable = hashtable;
        }
    }
}
```

## <a name="example"></a>Ejemplo

### <a name="description"></a>Descripción

El siguiente ejemplo de código se puede ver en Visual Studio para ver los resultados de aplicar <xref:System.Diagnostics.DebuggerDisplayAttribute> los <xref:System.Diagnostics.DebuggerBrowsableAttribute> atributos, y <xref:System.Diagnostics.DebuggerTypeProxyAttribute> .

### <a name="code"></a>Código

[!code-cpp[System.Diagnostics.DebuggerBrowsableAttribute#1](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.Diagnostics.DebuggerBrowsableAttribute/cpp/program.cpp#1)]
[!code-csharp[System.Diagnostics.DebuggerBrowsableAttribute#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.Diagnostics.DebuggerBrowsableAttribute/CS/program.cs#1)]
[!code-vb[System.Diagnostics.DebuggerBrowsableAttribute#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.Diagnostics.DebuggerBrowsableAttribute/VB/module1.vb#1)]

## <a name="see-also"></a>Consulte también

- <xref:System.Diagnostics.DebuggerDisplayAttribute>
- <xref:System.Diagnostics.DebuggerBrowsableAttribute>
- <xref:System.Diagnostics.DebuggerTypeProxyAttribute>
