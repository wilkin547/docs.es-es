---
title: "Lazy Initialization | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "lazy initialization in .NET, introduction"
ms.assetid: 56b4ae5c-4745-44ff-ad78-ffe4fcde6b9b
caps.latest.revision: 22
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 20
---
# Lazy Initialization
La *inicialización diferida* de un objeto significa que su creación se pospone hasta que se utiliza por primera vez. \(En este tema, los términos *inicialización diferida* y *creación de instancias diferida* son sinónimos.\) La inicialización diferida se utiliza principalmente para mejorar el rendimiento, evitar cálculos innecesarios y reducir los requisitos de memoria de los programas.  Estos son los escenarios más comunes:  
  
-   Cuando hay un objeto que resulta costoso crear y existe la posibilidad de que el programa no lo utilice.  Por ejemplo, supongamos que tiene en memoria un objeto `Customer` con una propiedad `Orders` que contiene una gran matriz de objetos `Order` que, para inicializarse, requiere una conexión a una base de datos.  Si el usuario nunca solicita que se muestren los pedidos ni se utilicen los datos en un cálculo, no existe ninguna razón para utilizar la memoria del sistema o los ciclos de cálculo para crearla.  Si se utiliza `Lazy<Orders>` para declarar el objeto `Orders` para su inicialización diferida, se puede evitar malgastar los recursos del sistema cuando no se utiliza el objeto.  
  
-   Cuando crear un objeto resulta costoso y se desea diferir su creación hasta que se hayan completado otras operaciones costosas.  Por ejemplo, supongamos que el programa carga varias instancias de objetos al iniciarse, pero que solo algunas de ellas se necesitan inmediatamente.  Puede mejorar el rendimiento de inicio del programa difiriendo la inicialización de los objetos que no se requieren hasta que se hayan creado los objetos necesarios.  
  
 Aunque puede escribir su propio código para realizar la inicialización diferida, recomendamos utilizar <xref:System.Lazy%601> en su lugar.  <xref:System.Lazy%601> y sus tipos relacionados también admiten la seguridad para subprocesos y proporcionan una directiva de propagación de excepciones coherente.  
  
 En la siguiente tabla se muestra una lista de los tipos que se proporcionan en la versión 4 de .NET Framework para habilitar la inicialización diferida en distintos escenarios.  
  
|Tipo|Descripción|  
|----------|-----------------|  
|<xref:System.Lazy%601>|Clase contenedora que proporciona semántica de inicialización diferida para cualquier biblioteca de clases o tipo definido por el usuario.|  
|<xref:System.Threading.ThreadLocal%601>|Se parece a <xref:System.Lazy%601>, con la diferencia de que proporciona la semántica de inicialización diferida para cada subproceso local.  Cada subproceso tiene el acceso a su propio valor único.|  
|<xref:System.Threading.LazyInitializer>|Proporciona métodos `static` avanzados \(`Shared` en Visual Basic\) para la inicialización diferida de objetos sin la sobrecarga de una clase.|  
  
## Inicialización diferida básica  
 Para definir un tipo inicializado diferido, por ejemplo, `MyType`, utilice `Lazy<MyType>` \(`Lazy(Of MyType)` en Visual Basic\), como se muestra en el siguiente ejemplo.  Si no se pasa ningún delegado en el constructor <xref:System.Lazy%601>, el tipo ajustado se crea mediante <xref:System.Activator.CreateInstance%2A?displayProperty=fullName> la primera vez que se tiene acceso a la propiedad de valor.  Si el tipo no tiene un constructor predeterminado, se produce una excepción en tiempo de ejecución.  
  
 En el siguiente ejemplo, supongamos que `Orders` es una clase que contiene una matriz de objetos `Order` recuperada de una base de datos.  Un objeto `Customer` contiene una instancia de `Orders`, pero dependiendo de las acciones del usuario, puede que no se necesiten los datos del objeto `Orders`.  
  
 [!code-csharp[Lazy#1](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#1)]
 [!code-vb[Lazy#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#1)]  
  
 También puede pasar un delegado en el constructor <xref:System.Lazy%601> que invoque una sobrecarga del constructor concreta en el tipo ajustado en el momento de la creación, y realizar los demás pasos de inicialización que se necesiten, como se muestra en el siguiente ejemplo.  
  
 [!code-csharp[Lazy#2](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#2)]
 [!code-vb[Lazy#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#2)]  
  
 Una vez creado el objeto Lazy, no se crea ninguna instancia de `Orders` hasta que se obtiene acceso por primera vez a la propiedad <xref:System.Lazy%601.Value%2A> de la variable Lazy.  La primera vez que se tiene acceso a ella, se crea y devuelve el tipo ajustado, y se almacena para cualquier acceso futuro.  
  
 [!code-csharp[Lazy#3](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#3)]
 [!code-vb[Lazy#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#3)]  
  
 Un objeto <xref:System.Lazy%601> siempre devuelve el mismo objeto o valor con el que se inicializó.  Por consiguiente, la propiedad <xref:System.Lazy%601.Value%2A> es de solo lectura.  Si <xref:System.Lazy%601.Value%2A> almacena un tipo de referencia, no se le puede asignar un nuevo objeto. \(Sin embargo, se puede cambiar el valor de sus campos y propiedades públicos que se pueden establecer.\) Si <xref:System.Lazy%601.Value%2A> almacena un tipo de valor, su valor no se puede modificar.  No obstante, puede crear una nueva variable invocando de nuevo el constructor de la variable con nuevos argumentos.  
  
 [!code-csharp[Lazy#4](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#4)]
 [!code-vb[Lazy#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#4)]  
  
 La nueva instancia diferida, al igual que la anterior, no crea ninguna instancia de `Orders` hasta que se tiene acceso a su propiedad <xref:System.Lazy%601.Value%2A> por primera vez.  
  
### Inicialización segura para subprocesos  
 De forma predeterminada, los objetos <xref:System.Lazy%601> son seguros para subprocesos.  Es decir, si el constructor no especifica el tipo de seguridad para subprocesos, los objetos <xref:System.Lazy%601> que cree serán seguros para subprocesos.  En escenarios multiproceso, el primer subproceso que tiene acceso a la propiedad <xref:System.Lazy%601.Value%2A> de un objeto <xref:System.Lazy%601> seguro para subprocesos la inicializa para todos los accesos subsiguientes en todos los subprocesos y para que todos los subprocesos compartan los mismos datos.  Por consiguiente, no importa qué subproceso inicializa el objeto y las condiciones de carrera son benignas.  
  
> [!NOTE]
>  Puede extender esta coherencia a las condiciones de error mediante el almacenamiento en caché de excepciones.  Para obtener más información, vea la siguiente sección, [Excepciones en los objetos diferidos](../../../docs/framework/performance/lazy-initialization.md#ExceptionsInLazyObjects).  
  
 En el ejemplo siguiente se muestra que la misma instancia de `Lazy<int>` tiene el mismo valor para tres subprocesos independientes.  
  
 [!code-csharp[Lazy#8](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#8)]
 [!code-vb[Lazy#8](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#8)]  
  
 Si necesita datos independientes en cada subproceso, utilice el tipo <xref:System.Threading.ThreadLocal%601>, como se describe más adelante en este tema.  
  
 Algunos constructores <xref:System.Lazy%601> tienen un parámetro booleano denominado `isThreadSafe` que se utiliza para especificar si se va a obtener acceso a la propiedad <xref:System.Lazy%601.Value%2A> desde varios subprocesos.  Si piensa tener acceso a la propiedad desde un solo subproceso, pase `false` para obtener una ventaja de rendimiento modesta.  Si piensa obtener acceso a la propiedad desde varios subprocesos, pase `true` para indicar a la instancia de <xref:System.Lazy%601> cómo controlar correctamente las condiciones de carrera en las que un subproceso producirá una excepción en el momento de la inicialización.  
  
 Algunos constructores <xref:System.Lazy%601> tienen un parámetro de <xref:System.Threading.LazyThreadSafetyMode> denominado `mode`.  Estos constructores proporcionan un modo adicional de seguridad para subprocesos.  En la siguiente tabla, se muestra cómo la seguridad para subprocesos de un objeto <xref:System.Lazy%601> se ve afectada por los parámetros de constructor que especifican la seguridad para subprocesos.  Cada constructor tiene como máximo un parámetro de este tipo.  
  
|Seguridad para subprocesos del objeto|Parámetro `mode` de `LazyThreadSafetyMode`|Parámetro booleano `isThreadSafe`|Ningún parámetro de seguridad para subprocesos|  
|-------------------------------------------|------------------------------------------------|---------------------------------------|----------------------------------------------------|  
|Totalmente seguro para subprocesos; solo un subproceso a la vez intenta inicializar el valor.|<xref:System.Threading.LazyThreadSafetyMode>|`true`|Sí.|  
|No es seguro para subprocesos.|<xref:System.Threading.LazyThreadSafetyMode>|`false`|No es aplicable|  
|Totalmente seguro para subprocesos; los subprocesos se precipitan a inicializar el valor.|<xref:System.Threading.LazyThreadSafetyMode>|No es aplicable|No es aplicable|  
  
 Tal y como se muestra en la tabla, especificar <xref:System.Threading.LazyThreadSafetyMode?displayProperty=fullName> para el parámetro `mode` equivale a especificar `true` para el parámetro `isThreadSafe`, y especificar <xref:System.Threading.LazyThreadSafetyMode?displayProperty=fullName> equivale a especificar `false`.  
  
 Si se especifica <xref:System.Threading.LazyThreadSafetyMode?displayProperty=fullName>, varios subprocesos podrán intentar inicializar la instancia de <xref:System.Lazy%601>.  Solo un subproceso podrá ganar esta carrera y todos los demás subprocesos recibirán el valor inicializado por el subproceso ganador.  Si se produce una excepción en un subproceso durante la inicialización, ese subproceso no recibirá el valor establecido por el subproceso ganador.  Las excepciones no se almacenan en la memoria caché, por lo que la próxima vez que se intente obtener acceso a la propiedad <xref:System.Lazy%601.Value%2A>, es posible que la inicialización se realice correctamente.  Esto difiere de la manera en que se tratan las excepciones en otros modos, lo cual se describe en la siguiente sección.  Para obtener más información, vea la enumeración <xref:System.Threading.LazyThreadSafetyMode>.  
  
<a name="ExceptionsInLazyObjects"></a>   
## Excepciones en los objetos diferidos  
 Tal y como se ha explicado anteriormente, un objeto <xref:System.Lazy%601> siempre devuelve el mismo objeto o valor con el que se inicializó y, por consiguiente, la propiedad <xref:System.Lazy%601.Value%2A> es de solo lectura.  Si habilita el almacenamiento en caché de excepciones, esta inmutabilidad también se extiende al comportamiento de las excepciones.  Si un objeto con inicialización diferida tiene habilitado el almacenamiento en caché de excepciones y produce una excepción desde su método de inicialización cuando se tiene acceso por primera vez a la propiedad <xref:System.Lazy%601.Value%2A>, esta misma excepción se producirá cada vez que se intente tener acceso a la propiedad <xref:System.Lazy%601.Value%2A>.  En otras palabras, nunca se vuelve a invocar el constructor del tipo encapsulado, ni siquiera en escenarios multiproceso.  Por tanto, el objeto <xref:System.Lazy%601> no puede producir una excepción en un acceso y devolver un valor en un acceso posterior.  
  
 El almacenamiento en caché de excepciones se habilita cuando se usa cualquier constructor <xref:System.Lazy%601?displayProperty=fullName> que toma un método de inicialización \(parámetro `valueFactory`\); por ejemplo, se habilita al usar el constructor `Lazy(T)(Func(T))`.  Si el constructor también toma un valor <xref:System.Threading.LazyThreadSafetyMode> \(parámetro `mode`\), especifique <xref:System.Threading.LazyThreadSafetyMode?displayProperty=fullName> o <xref:System.Threading.LazyThreadSafetyMode?displayProperty=fullName>.  Al especificar un método de inicialización se habilita el almacenamiento en caché de excepciones para estos dos modos.  El método de inicialización puede ser muy simple.  Por ejemplo, puede llamar al constructor predeterminado para `T`: `new Lazy<Contents>(() => new Contents(), mode)` en C\# o `New Lazy(Of Contents)(Function() New Contents())` en Visual Basic.  Si usa un constructor <xref:System.Lazy%601?displayProperty=fullName> que no especifica ningún método de inicialización, las excepciones producidas por el constructor predeterminado de `T` no se almacenan en memoria caché.  Para obtener más información, vea la enumeración <xref:System.Threading.LazyThreadSafetyMode>.  
  
> [!NOTE]
>  Si crea un objeto <xref:System.Lazy%601> con el parámetro de constructor `isThreadSafe` establecido en `false` o el parámetro de constructor `mode` establecido en <xref:System.Threading.LazyThreadSafetyMode?displayProperty=fullName>, debe tener acceso al objeto <xref:System.Lazy%601> desde un único subproceso o especificar su propia sincronización.  Esto se aplica a todos los aspectos del objeto, incluido el almacenamiento en caché de excepciones.  
  
 Tal y como se menciona en la sección anterior, los objetos <xref:System.Lazy%601> que se crean especificando <xref:System.Threading.LazyThreadSafetyMode?displayProperty=fullName> tratan las excepciones de manera diferente.  Con <xref:System.Threading.LazyThreadSafetyMode>, varios subprocesos pueden competir para inicializar la instancia de <xref:System.Lazy%601>.  En este caso, las excepciones no se almacenan en la memoria caché y se puede seguir intentando obtener acceso a la propiedad <xref:System.Lazy%601.Value%2A> hasta que la inicialización se realice correctamente.  
  
 En la tabla siguiente se resume la forma en que los constructores <xref:System.Lazy%601> controlan el almacenamiento en caché de excepciones.  
  
|Constructor|Modo de seguridad para subprocesos|Usa método de inicialización|Se almacenan en caché las excepciones|  
|-----------------|----------------------------------------|----------------------------------|-------------------------------------------|  
|Lazy\(T\)\(\)|\(<xref:> System.Threading.LazyThreadSafetyMode.ExecutionAndPublication?qualifyHint=False&autoUpgrade=True\)|No|No|  
|Lazy\(T\)\(Func\(T\)\)|\(<xref:> System.Threading.LazyThreadSafetyMode.ExecutionAndPublication?qualifyHint=False&autoUpgrade=True\)|Sí|Sí|  
|Lazy\(T\)\(Boolean\)|`True` \(<xref:> System.Threading.LazyThreadSafetyMode.ExecutionAndPublication?qualifyHint=False&autoUpgrade=True\) o `false` \(<xref:> System.Threading.LazyThreadSafetyMode.None?qualifyHint=False&autoUpgrade=True\)|No|No|  
|Lazy\(T\)\(Func\(T\), Boolean\)|`True` \(<xref:> System.Threading.LazyThreadSafetyMode.ExecutionAndPublication?qualifyHint=False&autoUpgrade=True\) o `false` \(<xref:> System.Threading.LazyThreadSafetyMode.None?qualifyHint=False&autoUpgrade=True\)|Sí|Sí|  
|Lazy\(T\)\(LazyThreadSafetyMode\)|Especificado por el usuario|No|No|  
|Lazy\(T\)\(Func\(T\), LazyThreadSafetyMode\)|Especificado por el usuario|Sí|No si el usuario especifica <xref:> System.Threading.LazyThreadSafetyMode.PublicationOnly?qualifyHint=False&autoUpgrade=True; de lo contrario, sí.|  
  
## Implementar una propiedad con inicialización diferida  
 Para implementar una propiedad pública mediante la inicialización diferida, defina el campo de respaldo de la propiedad en <xref:System.Lazy%601> y devuelva la propiedad <xref:System.Lazy%601.Value%2A> del descriptor de acceso `get` de la propiedad.  
  
 [!code-csharp[Lazy#5](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#5)]
 [!code-vb[Lazy#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#5)]  
  
 La propiedad <xref:System.Lazy%601.Value%2A> es de solo lectura; por consiguiente, la propiedad que la expone no tiene ningún descriptor de acceso `set`.  Si necesita que un objeto <xref:System.Lazy%601> respalde una propiedad de lectura y escritura, el descriptor de acceso `set` debe crear un nuevo objeto <xref:System.Lazy%601> y asignarlo a la memoria auxiliar.  El descriptor de acceso `set` debe crear una expresión lambda que devuelva el nuevo valor de propiedad que se pasó al descriptor de acceso `set` y debe pasar esa expresión lambda al constructor del nuevo objeto <xref:System.Lazy%601>.  La próxima vez que se obtenga acceso a la propiedad <xref:System.Lazy%601.Value%2A>, se inicializará el nuevo objeto <xref:System.Lazy%601> y, a continuación, su propiedad <xref:System.Lazy%601.Value%2A> devolverá el nuevo valor que se asignó a la propiedad.  El motivo de este complejo proceso reside en el mantenimiento de las protecciones multithreading integradas en <xref:System.Lazy%601>.  De lo contrario, los descriptores de acceso deberán almacenar en memoria caché el primer valor devuelto por la propiedad <xref:System.Lazy%601.Value%2A> y modificar únicamente dicho valor; para ello, el usuario deberá escribir su propio código seguro para subprocesos.  Debido a las inicializaciones adicionales que requiere una propiedad de lectura y escritura respaldada por un objeto <xref:System.Lazy%601>, el rendimiento podría no ser aceptable.  Además, según el escenario, es posible que sea necesaria una mayor coordinación para evitar condiciones de carrera entre los establecedores y los captadores.  
  
## Inicialización diferida local de subprocesos  
 En algunos escenarios multiproceso, puede que sea conveniente dar a cada subproceso sus propios datos privados.  Estos datos se denominan *datos locales de subprocesos*.  En la versión 3.5 de .NET Framework y en las versiones anteriores, se podría aplicar el atributo `ThreadStatic` a una variable estática para que fuese local de subprocesos.  Sin embargo, utilizar el atributo `ThreadStatic` puede dar lugar a errores sutiles.  Por ejemplo, incluso instrucciones de inicialización básicas harán se inicialice la variable únicamente en el primer subproceso que tenga acceso a ella, como se muestra en el siguiente ejemplo.  
  
 [!code-csharp[Lazy#6](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#6)]
 [!code-vb[Lazy#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#6)]  
  
 En todos los otros subprocesos, la variable se inicializará mediante su valor predeterminado \(cero\).  Como alternativa en la versión 4 de .NET Framework, puede utilizar el tipo <xref:System.Threading.ThreadLocal%601?displayProperty=fullName> para crear una variable basada en instancia y local de subprocesos que se inicializa en todos los subprocesos por el delegado <xref:System.Action%601> que le proporcione.  En el siguiente ejemplo, todos los subprocesos que tienen acceso a `counter` verán el valor de inicio 1.  
  
 [!code-csharp[Lazy#7](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#7)]
 [!code-vb[Lazy#7](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#7)]  
  
 <xref:System.Threading.ThreadLocal%601> se ajusta a su objeto de un modo muy similar a <xref:System.Lazy%601>, con estas diferencias esenciales:  
  
-   Cada subproceso inicializa la variable local de subprocesos mediante sus propios datos privados, a los que no se puede tener acceso desde otros subprocesos.  
  
-   La propiedad <xref:System.Threading.ThreadLocal%601.Value%2A?displayProperty=fullName> es de lectura y escritura y se puede modificar tantas veces como se desee.  Esto puede afectar a la propagación de excepciones; por ejemplo, una operación `get` podría producir una excepción y, la siguiente, inicializar el valor correctamente.  
  
-   Si no se proporciona ningún delegado de inicialización, <xref:System.Threading.ThreadLocal%601> inicializará su tipo ajustado utilizando el valor predeterminado del tipo.  En este sentido, <xref:System.Threading.ThreadLocal%601> es coherente con el atributo <xref:System.ThreadStaticAttribute>.  
  
 El siguiente ejemplo muestra que cada subproceso que tiene acceso a la instancia de `ThreadLocal<int>` obtiene su propia copia singular de los datos.  
  
 [!code-csharp[Lazy#9](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#9)]
 [!code-vb[Lazy#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#9)]  
  
## Variables locales de subprocesos de Parallel.For y ForEach  
 Cuando se utiliza el método <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=fullName> o el método <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=fullName> para recorrer en iteración los orígenes de datos en paralelo, se pueden utilizar las sobrecargas con compatibilidad integrada para los datos locales de subprocesos.  En estos métodos, el carácter local de subprocesos se logra utilizando delegados locales para crear los datos, tener acceso a ellos y limpiarlos.  Para obtener más información, vea [How to: Write a Parallel.For Loop with Thread\-Local Variables](../../../docs/standard/parallel-programming/how-to-write-a-parallel-for-loop-with-thread-local-variables.md) y [How to: Write a Parallel.ForEach Loop with Thread\-Local Variables](../../../docs/standard/parallel-programming/how-to-write-a-parallel-foreach-loop-with-thread-local-variables.md).  
  
## Utilizar la inicialización diferida para escenarios de sobrecarga baja  
 En los escenarios donde se tiene que inicializar en diferido un número grande de objetos, podría decidir que ajustar cada objeto en un objeto <xref:System.Lazy%601> exige demasiada memoria o demasiados recursos de cálculo.  O bien, puede suceder que tenga requisitos estrictos sobre cómo se expone la inicialización diferida.  En casos como este, puede utilizar los métodos `static``Shared` en Visual Basic\) de la clase <xref:System.Threading.LazyInitializer?displayProperty=fullName> para inicializar en diferido cada objeto sin ajustarlo en una instancia de <xref:System.Lazy%601>.  
  
 En el siguiente ejemplo, supongamos que, en lugar de ajustar un objeto `Orders` completo en un objeto <xref:System.Lazy%601>, los objetos `Order` individuales se inicializan en diferido solamente si es necesario.  
  
 [!code-csharp[Lazy#10](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#10)]
 [!code-vb[Lazy#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#10)]  
  
 En este ejemplo, observe que el procedimiento de inicialización se invoca en cada iteración del bucle.  En escenarios de varios subprocesos, el primer subproceso que invoca el procedimiento de inicialización es aquel cuyo valor ven todos los subprocesos.  Los subprocesos posteriores también invocan el procedimiento de inicialización, pero sus resultados no se utilizan.  Si este tipo de condición de carrera potencial no es aceptable, utilice la sobrecarga de <xref:System.Threading.LazyInitializer.EnsureInitialized%2A?displayProperty=fullName>, que toma un argumento Boolean y un objeto de sincronización.  
  
## Vea también  
 [Managed Threading Basics](../../../docs/standard/threading/managed-threading-basics.md)   
 [Threads and Threading](../../../docs/standard/threading/threads-and-threading.md)   
 [Task Parallel Library \(TPL\)](../../../docs/standard/parallel-programming/task-parallel-library-tpl.md)   
 [How to: Perform Lazy Initialization of Objects](../../../docs/framework/performance/how-to-perform-lazy-initialization-of-objects.md)