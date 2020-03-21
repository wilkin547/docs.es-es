---
title: Modelos de constructores seguros para objetos DependencyObject
ms.date: 03/30/2017
helpviewer_keywords:
- constructor patterns for dependency objects [WPF]
- dependency objects [WPF], constructor patterns
- FXCop tool [WPF]
ms.assetid: f704b81c-449a-47a4-ace1-9332e3cc6d60
ms.openlocfilehash: 6d6ff444b99ca893e687731c56a48ea3ac072dd0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187231"
---
# <a name="safe-constructor-patterns-for-dependencyobjects"></a>Modelos de constructores seguros para objetos DependencyObject
En general, los constructores de clase no deben llamar a devoluciones de llamada como métodos virtuales o delegados, porque se puede llamar a los constructores como inicialización base de constructores para una clase derivada. Es posible entrar en el método virtual en un estado de inicialización incompleto de cualquier objeto determinado. Pero el propio sistema de propiedades llama y expone internamente las devoluciones de llamada, como parte del sistema de propiedades de dependencia. Una operación tan simple como <xref:System.Windows.DependencyObject.SetValue%2A> establecer un valor de propiedad de dependencia con llamada potencialmente incluye una devolución de llamada en algún lugar de la determinación. Por esta razón, deben extremarse las precauciones al establecer los valores de propiedad de dependencia dentro del cuerpo de un constructor, algo que puede resultar problemático si el tipo se usa como una clase base. Hay un patrón <xref:System.Windows.DependencyObject> determinado para implementar constructores que evita problemas específicos con los estados de propiedad de dependencia y las devoluciones de llamada inherentes, que se documenta aquí.  

<a name="Property_System_Virtual_Methods"></a>
## <a name="property-system-virtual-methods"></a>Métodos virtuales del sistema de propiedades  
 Se puede llamar a los siguientes métodos virtuales <xref:System.Windows.DependencyObject.SetValue%2A> o devoluciones de <xref:System.Windows.ValidateValueCallback>llamada <xref:System.Windows.PropertyChangedCallback> <xref:System.Windows.CoerceValueCallback>durante <xref:System.Windows.DependencyObject.OnPropertyChanged%2A>los cálculos de la llamada que establece un valor de propiedad de dependencia: , , , . Cada uno de estos métodos virtuales o devoluciones de llamada sirve para una finalidad concreta dirigida a expandir la versatilidad del sistema de propiedades de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] y las propiedades de dependencia. Para más información sobre cómo usar estos métodos virtuales para personalizar la determinación de valores de propiedad, vea [Devoluciones de llamada y validación de las propiedades de dependencia](dependency-property-callbacks-and-validation.md).  
  
### <a name="fxcop-rule-enforcement-vs-property-system-virtuals"></a>FXCop Rule Enforcement vs. Property System Virtuals  
 Si usa la herramienta FXCop de Microsoft como parte del proceso de compilación, y deriva de algunas clases del marco de trabajo de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] llamando al constructor base, o bien implementa sus propias propiedades de dependencia en clases derivadas, es posible que se produzca una infracción de una regla de FXCop concreta. La cadena de nombre de esta infracción es:  
  
 `DoNotCallOverridableMethodsInConstructors`  
  
 Se trata de una regla que forma parte del conjunto de reglas público predeterminado de FXCop. Es posible que esta regla comunique la existencia de una traza a través del sistema de propiedades de dependencia que, llegado un punto, llama a un método virtual de dicho sistema. Esta infracción de la regla podría seguir apareciendo aunque se sigan los patrones de constructor recomendados que se documentan en este tema, en cuyo caso puede que sea necesario deshabilitar o suprimir esa regla en la configuración del conjunto de reglas de FXCop.  
  
### <a name="most-issues-come-from-deriving-classes-not-using-existing-classes"></a>La mayoría de los problemas proceden de derivar clases, no de usar las clases existentes  
 Los problemas que comunica esta regla se producen cuando se deriva de una clase que se implementa con métodos virtuales en su secuencia de construcción. Si sella la clase, o si sabe o exige de algún otro modo que no se derive de ella, las consideraciones que se explican aquí y los problemas que dan lugar a la regla de FXCop no son de aplicación en su caso. Pero si se crean clases previstas para su uso como clases base, como plantillas, o un conjunto ampliable de bibliotecas de controles, por ejemplo, entonces se deben seguir los patrones recomendados para los constructores.  
  
### <a name="default-constructors-must-initialize-all-values-requested-by-callbacks"></a>Los constructores predeterminados deben inicializar todos los valores solicitados por las devoluciones de llamada  
 Todos los miembros de instancia que utilizan las invalidaciones o devoluciones de llamada de clase (las devoluciones de llamada de la lista de la sección Virtuales del sistema de propiedades) deben inicializarse en el constructor sin parámetros de clase, incluso si algunos de esos valores se rellenan con valores "reales" a través de valores "reales" a través de valores "reales" a través de valores "reales" a través de valores "reales" a través de valores "reales" a través de valores "reales" a través de valores "reales" a través de parámetros de los constructores sin parámetros.  
  
 El código de ejemplo siguiente (y de los ejemplos siguientes) es un ejemplo de seudocódigo de C# que infringe esta regla y explica el problema:  
  
```csharp  
public class MyClass : DependencyObject  
{  
    public MyClass() {}  
    public MyClass(object toSetWobble)  
        : this()  
    {  
        Wobble = toSetWobble; //this is backed by a DependencyProperty  
        _myList = new ArrayList();    // this line should be in the default ctor  
    }  
    public static readonly DependencyProperty WobbleProperty =
        DependencyProperty.Register("Wobble", typeof(object), typeof(MyClass));  
    public object Wobble  
    {  
        get { return GetValue(WobbleProperty); }  
        set { SetValue(WobbleProperty, value); }  
    }  
    protected override void OnPropertyChanged(DependencyPropertyChangedEventArgs e)  
    {  
        int count = _myList.Count;    // null-reference exception  
    }  
    private ArrayList _myList;  
}  
```  
  
 Cuando el `new MyClass(objectvalue)`código de aplicación llama a , esto llama al constructor sin parámetros y constructores de clase base. `Property1 = object1`A continuación, establece , `OnPropertyChanged` que llama `MyClass` <xref:System.Windows.DependencyObject>al método virtual en la propiedad .  La invalidación hace referencia a `_myList`, que no se ha inicializado todavía.  
  
 Una manera de evitar estos problemas es asegurarse de que las devoluciones de llamada solo usan otras propiedades de dependencia, y que cada una de estas últimas tiene un valor predeterminado establecido como parte de sus metadatos registrados.  
  
<a name="Safe_Constructor_Patterns"></a>
## <a name="safe-constructor-patterns"></a>Patrones de constructor seguros  
 Para evitar los riesgos de inicialización incompleta si la clase se usa como clase base, siga estos patrones:  
  
#### <a name="parameterless-constructors-calling-base-initialization"></a>Constructores sin parámetros que llaman a la inicialización base  
 Implemente estos constructores llamando al valor predeterminado base:  
  
```csharp  
public MyClass : SomeBaseClass {  
    public MyClass() : base() {  
        // ALL class initialization, including initial defaults for
        // possible values that other ctors specify or that callbacks need.  
    }  
}  
```  
  
#### <a name="non-default-convenience-constructors-not-matching-any-base-signatures"></a>Constructores no predeterminados (útiles) que no coinciden con ninguna firma base  
 Si estos constructores usan los parámetros para establecer propiedades de dependencia en la inicialización, primero llame a su propio constructor sin parámetros de clase para la inicialización y, a continuación, use los parámetros para establecer las propiedades de dependencia. Pueden ser propiedades de dependencia definidas por la clase o bien heredadas de las clases base, pero debe usar el patrón siguiente en cualquier caso:  
  
```csharp  
public MyClass : SomeBaseClass {  
    public MyClass(object toSetProperty1) : this() {  
        // Class initialization NOT done by default.  
        // Then, set properties to values as passed in ctor parameters.  
        Property1 = toSetProperty1;  
    }  
}  
```  
  
#### <a name="non-default-convenience-constructors-which-do-match-base-signatures"></a>Constructores no predeterminados (útiles) que coinciden con firmas base  
 En lugar de llamar al constructor base con la misma parametrización, llame de nuevo al constructor sin parámetros de su propia clase. No llame al inicializador base, en su lugar debe llamar a `this()`. Después, reproduzca el comportamiento del constructor original mediante los parámetros pasados como valores para establecer las propiedades pertinentes. Use la documentación del constructor base original para obtener orientación para determinar las propiedades que debe establecer cada parámetro concreto:  
  
```csharp  
public MyClass : SomeBaseClass {  
    public MyClass(object toSetProperty1) : this() {  
        // Class initialization NOT done by default.  
        // Then, set properties to values as passed in ctor parameters.  
        Property1 = toSetProperty1;  
    }  
}  
```  
  
#### <a name="must-match-all-signatures"></a>Debe hacer coincidir todas las firmas  
 Para los casos en los que el tipo base tiene varias firmas, debe hacer coincidir deliberadamente todas las firmas posibles con una implementación de constructor propia que utilice el patrón recomendado de llamar al constructor sin parámetros de clase antes de establecer más Propiedades.  
  
#### <a name="setting-dependency-properties-with-setvalue"></a>Establecer propiedades de dependencia con SetValue  
 Estos mismos patrones se aplican si establece una propiedad que no tiene un <xref:System.Windows.DependencyObject.SetValue%2A>contenedor para la comodidad de configuración de propiedades y establece valores con . Las llamadas a ese paso a <xref:System.Windows.DependencyObject.SetValue%2A> través de parámetros de constructor también deben llamar al constructor sin parámetros de la clase para la inicialización.  
  
## <a name="see-also"></a>Consulte también

- [Propiedades de dependencia personalizadas](custom-dependency-properties.md)
- [Descripción general de las propiedades de dependencia](dependency-properties-overview.md)
- [Seguridad de las propiedades de dependencia](dependency-property-security.md)
