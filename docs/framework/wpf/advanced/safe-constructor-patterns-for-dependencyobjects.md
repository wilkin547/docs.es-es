---
title: "Modelos de constructores seguros para objetos DependencyObject | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "patrones de constructores para objetos de dependencia"
  - "objetos de dependencia, patrones de constructor"
  - "FXCop (herramienta)"
ms.assetid: f704b81c-449a-47a4-ace1-9332e3cc6d60
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Modelos de constructores seguros para objetos DependencyObject
En general, los constructores de clase no deben llamar a devoluciones de llamada como métodos virtuales o delegados, porque se puede llamar a los constructores como inicialización base de constructores para una clase derivada.  Podría entrarse en el método virtual en un estado de inicialización incompleto de cualquier objeto determinado.  Sin embargo, el propio sistema de propiedades llama y expone internamente devoluciones de llamada, como parte del sistema de propiedades de dependencia.  Una operación tan simple como establecer un valor de propiedad de dependencia con una llamada a <xref:System.Windows.DependencyObject.SetValue%2A>, incluye potencialmente una devolución de llamada en algún punto de la determinación.  Por esta razón, deben extremarse las precauciones al establecer los valores de propiedades de dependencia dentro del cuerpo de un constructor, algo que puede resultar problemático si el tipo se utiliza como clase base.  Existe un modelo concreto para implementar constructores <xref:System.Windows.DependencyObject> que evita los problemas concretos con los estados de las propiedades de dependencia y las devoluciones de llamada inherentes, que se documenta aquí.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="Property_System_Virtual_Methods"></a>   
## Métodos virtuales del sistema de propiedades  
 Potencialmente, se llama a los métodos virtuales o devoluciones de llamada siguientes durante los cálculos de la llamada a <xref:System.Windows.DependencyObject.SetValue%2A> que establece un valor de propiedad de dependencia: <xref:System.Windows.ValidateValueCallback>, <xref:System.Windows.PropertyChangedCallback>, <xref:System.Windows.CoerceValueCallback>, <xref:System.Windows.DependencyObject.OnPropertyChanged%2A>.  Cada uno de estos métodos virtuales o devoluciones de llamada sirve para una finalidad concreta dirigida a expandir la versatilidad del sistema de propiedades de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] y las propiedades de dependencia.  Para obtener más información sobre cómo utilizar estos métodos virtuales para personalizar la determinación de valores de propiedad, vea [Devoluciones de llamada y validación de las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-callbacks-and-validation.md).  
  
### Aplicación de las reglas de FXCop con respecto alos métodos virtuales del sistema de propiedades  
 Si utiliza la herramienta FXCop de Microsoft como parte del proceso de compilación, y deriva de algunas clases del marco de trabajo de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] llamando al constructor base o bien implementa sus propias propiedades de dependencia en clases derivadas, podría producirse una infracción de una regla de FXCop concreta.  La cadena de nombre de esta infracción es:  
  
 `DoNotCallOverridableMethodsInConstructors`  
  
 Se trata de una regla que forma parte del conjunto de reglas público predeterminado de FXCop.  Posiblemente, lo que comunica esta regla es la existencia de una traza a través del sistema de propiedades de dependencia que, llegado un punto, llama a un método virtual de dicho sistema.  Esta infracción de la regla podría seguir apareciendo aunque se sigan los modelos de constructor recomendados que se documentan en este tema, en cuyo caso puede que sea necesario deshabilitar dicha regla en la configuración del conjunto de reglas de FXCop.  
  
### La mayoría de los problemas proceden de derivar clases, no de usar las clases existentes  
 Los problemas que comunica esta regla se producen cuando se deriva de una clase que se implementa con métodos virtuales en su secuencia de construcción.  Si sella la clase, o si sabe o exige de algún otro modo que no se deriva de ella, las consideraciones que se explican aquí y los problemas que dan lugar a la regla de FXCop no son de aplicación en su caso.  Sin embargo, si crea clases previstas para su uso como clases base, como plantillas, o un conjunto ampliable de bibliotecas de controles, por ejemplo, entonces debe seguir los modelos recomendados para los constructores.  
  
### Los constructores predeterminados deben inicializar todos los valores solicitados por las devoluciones de llamada  
 Cualquier miembro de instancia que se utilice en las invalidaciones o devoluciones de llamada de la clase \(las devoluciones de llamada de la lista de la sección Métodos virtuales del sistema de propiedades\) se deben inicializar en el constructor predeterminado de la clase aunque algunos de esos valores se rellenen mediante valores "reales" a través de los parámetros de los constructores no predeterminados.  
  
 En el código de ejemplo siguiente \(y de los ejemplos subsiguientes\) es un ejemplo de pseudocódigo en C\# que infringe esta regla y explica el problema:  
  
```  
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
  
 Cuando el código de aplicación llama a `new MyClass(objectvalue)`, se llama al constructor predeterminado y a los constructores de clase base.  A continuación, se establece `Property1 = object1`, que llama al método virtual `OnPropertyChanged` del objeto <xref:System.Windows.DependencyObject> `MyClass` poseedor.  La invalidación hace referencia a `_myList`, que no se ha inicializado todavía.  
  
 Una manera de evitar estos problemas es asegurarse de que las devoluciones de llamada sólo utilizan otras propiedades de dependencia, y que cada una de éstas últimas tiene un valor predeterminado establecido como parte de sus metadatos registrados.  
  
<a name="Safe_Constructor_Patterns"></a>   
## Modelos de constructor seguros  
 Para evitar los riesgos de inicialización incompleta si la clase se utiliza como clase base, siga estos modelos:  
  
#### Constructores predeterminados que llaman a la inicialización base  
 Implemente estos constructores llamando al valor predeterminado base:  
  
```  
public MyClass : SomeBaseClass {  
    public MyClass() : base() {  
        // ALL class initialization, including initial defaults for   
        // possible values that other ctors specify or that callbacks need.  
    }  
}  
```  
  
#### Constructores no predeterminados \(útiles\), que no coinciden con ninguna firma base  
 Si estos constructores utilizan los parámetros para establecer las propiedades de dependencia en la inicialización, llame primero al constructor predeterminado de su propia clase para la inicialización y, a continuación, utilice los parámetros para establecer las propiedades de dependencia.  Pueden ser propiedades de dependencia definidas por la clase o bien heredadas de las clases base, pero debe utilizar el modelo siguiente en cualquier caso:  
  
```  
public MyClass : SomeBaseClass {  
    public MyClass(object toSetProperty1) : this() {  
        // Class initialization NOT done by default.  
        // Then, set properties to values as passed in ctor parameters.  
        Property1 = toSetProperty1;  
    }  
}  
```  
  
#### Constructores no predeterminados \(útiles\), que coinciden con firmas base  
 En lugar de llamar al constructor base con la misma parametrización, llame de nuevo al constructor predeterminado de su propia clase.  No llame al inicializador base; en su lugar debe llamar a `this()`.  A continuación, reproduzca el comportamiento del constructor original utilizando los parámetros pasados como valores para establecer las propiedades pertinentes.  Utilice la documentación del constructor base original a fin de obtener orientación para determinar las propiedades que debe establecer cada parámetro concreto:  
  
```  
public MyClass : SomeBaseClass {  
    public MyClass(object toSetProperty1) : this() {  
        // Class initialization NOT done by default.  
        // Then, set properties to values as passed in ctor parameters.  
        Property1 = toSetProperty1;  
    }  
}  
```  
  
#### Debe hacer coincidir todas las firmas  
 Para aquellos caso en que el tipo base tiene varias firmas, debe hacer coincidir deliberadamente todas las firmas posibles con una implementación de constructor propia que utilice el modelo recomendado consistente en llamar al constructor predeterminado de clase antes de establecer otras propiedades.  
  
#### Establecer propiedades de dependencia con SetValue  
 Estos mismos modelos se aplican si establece una propiedad que no tiene un contenedor para facilitar el establecimiento de propiedades, y establece los valores con <xref:System.Windows.DependencyObject.SetValue%2A>.  Las llamadas al método <xref:System.Windows.DependencyObject.SetValue%2A> que atraviesa los parámetros del constructor también deben llamar al constructor predeterminado de la clase para la inicialización.  
  
## Vea también  
 [Propiedades de dependencia personalizadas](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)   
 [Información general sobre las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [Seguridad de las propiedades de dependencia](../../../../docs/framework/wpf/advanced/dependency-property-security.md)