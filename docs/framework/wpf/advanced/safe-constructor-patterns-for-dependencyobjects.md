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
# <a name="safe-constructor-patterns-for-dependencyobjects"></a><span data-ttu-id="d1b16-102">Modelos de constructores seguros para objetos DependencyObject</span><span class="sxs-lookup"><span data-stu-id="d1b16-102">Safe Constructor Patterns for DependencyObjects</span></span>
<span data-ttu-id="d1b16-103">En general, los constructores de clase no deben llamar a devoluciones de llamada como métodos virtuales o delegados, porque se puede llamar a los constructores como inicialización base de constructores para una clase derivada.</span><span class="sxs-lookup"><span data-stu-id="d1b16-103">Generally, class constructors should not call callbacks such as virtual methods or delegates, because constructors can be called as base initialization of constructors for a derived class.</span></span> <span data-ttu-id="d1b16-104">Es posible entrar en el método virtual en un estado de inicialización incompleto de cualquier objeto determinado.</span><span class="sxs-lookup"><span data-stu-id="d1b16-104">Entering the virtual might be done at an incomplete initialization state of any given object.</span></span> <span data-ttu-id="d1b16-105">Pero el propio sistema de propiedades llama y expone internamente las devoluciones de llamada, como parte del sistema de propiedades de dependencia.</span><span class="sxs-lookup"><span data-stu-id="d1b16-105">However, the property system itself calls and exposes callbacks internally, as part of the dependency property system.</span></span> <span data-ttu-id="d1b16-106">Una operación tan simple como <xref:System.Windows.DependencyObject.SetValue%2A> establecer un valor de propiedad de dependencia con llamada potencialmente incluye una devolución de llamada en algún lugar de la determinación.</span><span class="sxs-lookup"><span data-stu-id="d1b16-106">As simple an operation as setting a dependency property value with <xref:System.Windows.DependencyObject.SetValue%2A> call potentially includes a callback somewhere in the determination.</span></span> <span data-ttu-id="d1b16-107">Por esta razón, deben extremarse las precauciones al establecer los valores de propiedad de dependencia dentro del cuerpo de un constructor, algo que puede resultar problemático si el tipo se usa como una clase base.</span><span class="sxs-lookup"><span data-stu-id="d1b16-107">For this reason, you should be careful when setting dependency property values within the body of a constructor, which can become problematic if your type is used as a base class.</span></span> <span data-ttu-id="d1b16-108">Hay un patrón <xref:System.Windows.DependencyObject> determinado para implementar constructores que evita problemas específicos con los estados de propiedad de dependencia y las devoluciones de llamada inherentes, que se documenta aquí.</span><span class="sxs-lookup"><span data-stu-id="d1b16-108">There is a particular pattern for implementing <xref:System.Windows.DependencyObject> constructors that avoids specific problems with dependency property states and the inherent callbacks, which is documented here.</span></span>  

<a name="Property_System_Virtual_Methods"></a>
## <a name="property-system-virtual-methods"></a><span data-ttu-id="d1b16-109">Métodos virtuales del sistema de propiedades</span><span class="sxs-lookup"><span data-stu-id="d1b16-109">Property System Virtual Methods</span></span>  
 <span data-ttu-id="d1b16-110">Se puede llamar a los siguientes métodos virtuales <xref:System.Windows.DependencyObject.SetValue%2A> o devoluciones de <xref:System.Windows.ValidateValueCallback>llamada <xref:System.Windows.PropertyChangedCallback> <xref:System.Windows.CoerceValueCallback>durante <xref:System.Windows.DependencyObject.OnPropertyChanged%2A>los cálculos de la llamada que establece un valor de propiedad de dependencia: , , , .</span><span class="sxs-lookup"><span data-stu-id="d1b16-110">The following virtual methods or callbacks are potentially called during the computations of the <xref:System.Windows.DependencyObject.SetValue%2A> call that sets a dependency property value: <xref:System.Windows.ValidateValueCallback>, <xref:System.Windows.PropertyChangedCallback>, <xref:System.Windows.CoerceValueCallback>, <xref:System.Windows.DependencyObject.OnPropertyChanged%2A>.</span></span> <span data-ttu-id="d1b16-111">Cada uno de estos métodos virtuales o devoluciones de llamada sirve para una finalidad concreta dirigida a expandir la versatilidad del sistema de propiedades de [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] y las propiedades de dependencia.</span><span class="sxs-lookup"><span data-stu-id="d1b16-111">Each of these virtual methods or callbacks serves a particular purpose in expanding the versatility of the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] property system and dependency properties.</span></span> <span data-ttu-id="d1b16-112">Para más información sobre cómo usar estos métodos virtuales para personalizar la determinación de valores de propiedad, vea [Devoluciones de llamada y validación de las propiedades de dependencia](dependency-property-callbacks-and-validation.md).</span><span class="sxs-lookup"><span data-stu-id="d1b16-112">For more information on how to use these virtuals to customize property value determination, see [Dependency Property Callbacks and Validation](dependency-property-callbacks-and-validation.md).</span></span>  
  
### <a name="fxcop-rule-enforcement-vs-property-system-virtuals"></a><span data-ttu-id="d1b16-113">FXCop Rule Enforcement vs. Property System Virtuals</span><span class="sxs-lookup"><span data-stu-id="d1b16-113">FXCop Rule Enforcement vs. Property System Virtuals</span></span>  
 <span data-ttu-id="d1b16-114">Si usa la herramienta FXCop de Microsoft como parte del proceso de compilación, y deriva de algunas clases del marco de trabajo de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] llamando al constructor base, o bien implementa sus propias propiedades de dependencia en clases derivadas, es posible que se produzca una infracción de una regla de FXCop concreta.</span><span class="sxs-lookup"><span data-stu-id="d1b16-114">If you use the Microsoft tool FXCop as part of your build process, and you either derive from certain [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] framework classes calling the base constructor, or implement your own dependency properties on derived classes, you might encounter a particular FXCop rule violation.</span></span> <span data-ttu-id="d1b16-115">La cadena de nombre de esta infracción es:</span><span class="sxs-lookup"><span data-stu-id="d1b16-115">The name string for this violation is:</span></span>  
  
 `DoNotCallOverridableMethodsInConstructors`  
  
 <span data-ttu-id="d1b16-116">Se trata de una regla que forma parte del conjunto de reglas público predeterminado de FXCop.</span><span class="sxs-lookup"><span data-stu-id="d1b16-116">This is a rule that is part of the default public rule set for FXCop.</span></span> <span data-ttu-id="d1b16-117">Es posible que esta regla comunique la existencia de una traza a través del sistema de propiedades de dependencia que, llegado un punto, llama a un método virtual de dicho sistema.</span><span class="sxs-lookup"><span data-stu-id="d1b16-117">What this rule might be reporting is a trace through the dependency property system that eventually calls a dependency property system virtual method.</span></span> <span data-ttu-id="d1b16-118">Esta infracción de la regla podría seguir apareciendo aunque se sigan los patrones de constructor recomendados que se documentan en este tema, en cuyo caso puede que sea necesario deshabilitar o suprimir esa regla en la configuración del conjunto de reglas de FXCop.</span><span class="sxs-lookup"><span data-stu-id="d1b16-118">This rule violation might continue to appear even after following the recommended constructor patterns documented in this topic, so you might need to disable or suppress that rule in your FXCop rule set configuration.</span></span>  
  
### <a name="most-issues-come-from-deriving-classes-not-using-existing-classes"></a><span data-ttu-id="d1b16-119">La mayoría de los problemas proceden de derivar clases, no de usar las clases existentes</span><span class="sxs-lookup"><span data-stu-id="d1b16-119">Most Issues Come From Deriving Classes, Not Using Existing Classes</span></span>  
 <span data-ttu-id="d1b16-120">Los problemas que comunica esta regla se producen cuando se deriva de una clase que se implementa con métodos virtuales en su secuencia de construcción.</span><span class="sxs-lookup"><span data-stu-id="d1b16-120">The issues reported by this rule occur when a class that you implement with virtual methods in its construction sequence is then derived from.</span></span> <span data-ttu-id="d1b16-121">Si sella la clase, o si sabe o exige de algún otro modo que no se derive de ella, las consideraciones que se explican aquí y los problemas que dan lugar a la regla de FXCop no son de aplicación en su caso.</span><span class="sxs-lookup"><span data-stu-id="d1b16-121">If you seal your class, or otherwise know or enforce that your class will not be derived from, the considerations explained here and the issues that motivated the FXCop rule do not apply to you.</span></span> <span data-ttu-id="d1b16-122">Pero si se crean clases previstas para su uso como clases base, como plantillas, o un conjunto ampliable de bibliotecas de controles, por ejemplo, entonces se deben seguir los patrones recomendados para los constructores.</span><span class="sxs-lookup"><span data-stu-id="d1b16-122">However, if you are authoring classes in such a way that they are intended to be used as base classes, for instance if you are creating templates, or an expandable control library set, you should follow the patterns recommended here for constructors.</span></span>  
  
### <a name="default-constructors-must-initialize-all-values-requested-by-callbacks"></a><span data-ttu-id="d1b16-123">Los constructores predeterminados deben inicializar todos los valores solicitados por las devoluciones de llamada</span><span class="sxs-lookup"><span data-stu-id="d1b16-123">Default Constructors Must Initialize All Values Requested By Callbacks</span></span>  
 <span data-ttu-id="d1b16-124">Todos los miembros de instancia que utilizan las invalidaciones o devoluciones de llamada de clase (las devoluciones de llamada de la lista de la sección Virtuales del sistema de propiedades) deben inicializarse en el constructor sin parámetros de clase, incluso si algunos de esos valores se rellenan con valores "reales" a través de valores "reales" a través de valores "reales" a través de valores "reales" a través de valores "reales" a través de valores "reales" a través de valores "reales" a través de valores "reales" a través de parámetros de los constructores sin parámetros.</span><span class="sxs-lookup"><span data-stu-id="d1b16-124">Any instance members that are used by your class overrides or callbacks (the callbacks from the list in the Property System Virtuals section) must be initialized in your class parameterless constructor, even if some of those values are filled by "real" values through parameters of the nonparameterless constructors.</span></span>  
  
 <span data-ttu-id="d1b16-125">El código de ejemplo siguiente (y de los ejemplos siguientes) es un ejemplo de seudocódigo de C# que infringe esta regla y explica el problema:</span><span class="sxs-lookup"><span data-stu-id="d1b16-125">The following example code (and subsequent examples) is a pseudo-C# example that violates this rule and explains the problem:</span></span>  
  
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
  
 <span data-ttu-id="d1b16-126">Cuando el `new MyClass(objectvalue)`código de aplicación llama a , esto llama al constructor sin parámetros y constructores de clase base.</span><span class="sxs-lookup"><span data-stu-id="d1b16-126">When application code calls `new MyClass(objectvalue)`, this calls the parameterless constructor and base class constructors.</span></span> <span data-ttu-id="d1b16-127">`Property1 = object1`A continuación, establece , `OnPropertyChanged` que llama `MyClass` <xref:System.Windows.DependencyObject>al método virtual en la propiedad .</span><span class="sxs-lookup"><span data-stu-id="d1b16-127">Then it sets `Property1 = object1`, which calls the virtual method `OnPropertyChanged` on the owning `MyClass` <xref:System.Windows.DependencyObject>.</span></span>  <span data-ttu-id="d1b16-128">La invalidación hace referencia a `_myList`, que no se ha inicializado todavía.</span><span class="sxs-lookup"><span data-stu-id="d1b16-128">The override refers to `_myList`, which has not been initialized yet.</span></span>  
  
 <span data-ttu-id="d1b16-129">Una manera de evitar estos problemas es asegurarse de que las devoluciones de llamada solo usan otras propiedades de dependencia, y que cada una de estas últimas tiene un valor predeterminado establecido como parte de sus metadatos registrados.</span><span class="sxs-lookup"><span data-stu-id="d1b16-129">One way to avoid these issues is to make sure that callbacks use only other dependency properties, and that each such dependency property has an established default value as part of its registered metadata.</span></span>  
  
<a name="Safe_Constructor_Patterns"></a>
## <a name="safe-constructor-patterns"></a><span data-ttu-id="d1b16-130">Patrones de constructor seguros</span><span class="sxs-lookup"><span data-stu-id="d1b16-130">Safe Constructor Patterns</span></span>  
 <span data-ttu-id="d1b16-131">Para evitar los riesgos de inicialización incompleta si la clase se usa como clase base, siga estos patrones:</span><span class="sxs-lookup"><span data-stu-id="d1b16-131">To avoid the risks of incomplete initialization if your class is used as a base class, follow these patterns:</span></span>  
  
#### <a name="parameterless-constructors-calling-base-initialization"></a><span data-ttu-id="d1b16-132">Constructores sin parámetros que llaman a la inicialización base</span><span class="sxs-lookup"><span data-stu-id="d1b16-132">Parameterless constructors calling base initialization</span></span>  
 <span data-ttu-id="d1b16-133">Implemente estos constructores llamando al valor predeterminado base:</span><span class="sxs-lookup"><span data-stu-id="d1b16-133">Implement these constructors calling the base default:</span></span>  
  
```csharp  
public MyClass : SomeBaseClass {  
    public MyClass() : base() {  
        // ALL class initialization, including initial defaults for
        // possible values that other ctors specify or that callbacks need.  
    }  
}  
```  
  
#### <a name="non-default-convenience-constructors-not-matching-any-base-signatures"></a><span data-ttu-id="d1b16-134">Constructores no predeterminados (útiles) que no coinciden con ninguna firma base</span><span class="sxs-lookup"><span data-stu-id="d1b16-134">Non-default (convenience) constructors, not matching any base signatures</span></span>  
 <span data-ttu-id="d1b16-135">Si estos constructores usan los parámetros para establecer propiedades de dependencia en la inicialización, primero llame a su propio constructor sin parámetros de clase para la inicialización y, a continuación, use los parámetros para establecer las propiedades de dependencia.</span><span class="sxs-lookup"><span data-stu-id="d1b16-135">If these constructors use the parameters to set dependency properties in the initialization, first call your own class parameterless constructor for initialization, and then use the parameters to set dependency properties.</span></span> <span data-ttu-id="d1b16-136">Pueden ser propiedades de dependencia definidas por la clase o bien heredadas de las clases base, pero debe usar el patrón siguiente en cualquier caso:</span><span class="sxs-lookup"><span data-stu-id="d1b16-136">These could either be dependency properties defined by your class, or dependency properties inherited from base classes, but in either case use the following pattern:</span></span>  
  
```csharp  
public MyClass : SomeBaseClass {  
    public MyClass(object toSetProperty1) : this() {  
        // Class initialization NOT done by default.  
        // Then, set properties to values as passed in ctor parameters.  
        Property1 = toSetProperty1;  
    }  
}  
```  
  
#### <a name="non-default-convenience-constructors-which-do-match-base-signatures"></a><span data-ttu-id="d1b16-137">Constructores no predeterminados (útiles) que coinciden con firmas base</span><span class="sxs-lookup"><span data-stu-id="d1b16-137">Non-default (convenience) constructors, which do match base signatures</span></span>  
 <span data-ttu-id="d1b16-138">En lugar de llamar al constructor base con la misma parametrización, llame de nuevo al constructor sin parámetros de su propia clase.</span><span class="sxs-lookup"><span data-stu-id="d1b16-138">Instead of calling the base constructor with the same parameterization, again call your own class' parameterless constructor.</span></span> <span data-ttu-id="d1b16-139">No llame al inicializador base, en su lugar debe llamar a `this()`.</span><span class="sxs-lookup"><span data-stu-id="d1b16-139">Do not call the base initializer; instead you should call `this()`.</span></span> <span data-ttu-id="d1b16-140">Después, reproduzca el comportamiento del constructor original mediante los parámetros pasados como valores para establecer las propiedades pertinentes.</span><span class="sxs-lookup"><span data-stu-id="d1b16-140">Then reproduce the original constructor behavior by using the passed parameters as values for setting the relevant properties.</span></span> <span data-ttu-id="d1b16-141">Use la documentación del constructor base original para obtener orientación para determinar las propiedades que debe establecer cada parámetro concreto:</span><span class="sxs-lookup"><span data-stu-id="d1b16-141">Use the original base constructor documentation for guidance in determining the properties that the particular parameters are intended to set:</span></span>  
  
```csharp  
public MyClass : SomeBaseClass {  
    public MyClass(object toSetProperty1) : this() {  
        // Class initialization NOT done by default.  
        // Then, set properties to values as passed in ctor parameters.  
        Property1 = toSetProperty1;  
    }  
}  
```  
  
#### <a name="must-match-all-signatures"></a><span data-ttu-id="d1b16-142">Debe hacer coincidir todas las firmas</span><span class="sxs-lookup"><span data-stu-id="d1b16-142">Must match all signatures</span></span>  
 <span data-ttu-id="d1b16-143">Para los casos en los que el tipo base tiene varias firmas, debe hacer coincidir deliberadamente todas las firmas posibles con una implementación de constructor propia que utilice el patrón recomendado de llamar al constructor sin parámetros de clase antes de establecer más Propiedades.</span><span class="sxs-lookup"><span data-stu-id="d1b16-143">For cases where the base type has multiple signatures, you must deliberately match all possible signatures with a constructor implementation of your own that uses the recommended pattern of calling the class parameterless constructor before setting further properties.</span></span>  
  
#### <a name="setting-dependency-properties-with-setvalue"></a><span data-ttu-id="d1b16-144">Establecer propiedades de dependencia con SetValue</span><span class="sxs-lookup"><span data-stu-id="d1b16-144">Setting dependency properties with SetValue</span></span>  
 <span data-ttu-id="d1b16-145">Estos mismos patrones se aplican si establece una propiedad que no tiene un <xref:System.Windows.DependencyObject.SetValue%2A>contenedor para la comodidad de configuración de propiedades y establece valores con .</span><span class="sxs-lookup"><span data-stu-id="d1b16-145">These same patterns apply if you are setting a property that does not have a wrapper for property setting convenience, and set values with <xref:System.Windows.DependencyObject.SetValue%2A>.</span></span> <span data-ttu-id="d1b16-146">Las llamadas a ese paso a <xref:System.Windows.DependencyObject.SetValue%2A> través de parámetros de constructor también deben llamar al constructor sin parámetros de la clase para la inicialización.</span><span class="sxs-lookup"><span data-stu-id="d1b16-146">Your calls to <xref:System.Windows.DependencyObject.SetValue%2A> that pass through constructor parameters should also call the class' parameterless constructor for initialization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1b16-147">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d1b16-147">See also</span></span>

- [<span data-ttu-id="d1b16-148">Propiedades de dependencia personalizadas</span><span class="sxs-lookup"><span data-stu-id="d1b16-148">Custom Dependency Properties</span></span>](custom-dependency-properties.md)
- [<span data-ttu-id="d1b16-149">Descripción general de las propiedades de dependencia</span><span class="sxs-lookup"><span data-stu-id="d1b16-149">Dependency Properties Overview</span></span>](dependency-properties-overview.md)
- [<span data-ttu-id="d1b16-150">Seguridad de las propiedades de dependencia</span><span class="sxs-lookup"><span data-stu-id="d1b16-150">Dependency Property Security</span></span>](dependency-property-security.md)
