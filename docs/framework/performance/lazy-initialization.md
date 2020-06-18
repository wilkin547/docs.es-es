---
title: Inicialización diferida
description: Explore la inicialización diferida en .NET, una mejora del rendimiento que significa que la creación de un objeto se aplaza hasta que el objeto se use por primera vez.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lazy initialization in .NET, introduction
ms.assetid: 56b4ae5c-4745-44ff-ad78-ffe4fcde6b9b
ms.openlocfilehash: 355fa326fc19e9a50a74e21ace0a6353f5c740c5
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904239"
---
# <a name="lazy-initialization"></a>Inicialización diferida
La *inicialización diferida* de un objeto implica que su creación se aplaza hasta que se usa por primera vez. (En este tema, los términos *inicialización diferida* y *creación de instancias diferidas* son sinónimos). La inicialización diferida se utiliza principalmente para mejorar el rendimiento, evitar el cálculo excesivo y reducir los requisitos de memoria del programa. Estos son los escenarios más comunes:  
  
- Cuando hay un objeto costoso de crear y es posible que el programa no lo use. Por ejemplo, supongamos que tiene en memoria un objeto `Customer` con una propiedad `Orders` que contiene una matriz grande de objetos `Order` que, para inicializarse, requieren una conexión de base de datos. Si el usuario nunca solicita que se muestre Orders y nunca usa los datos en un cálculo, no hay ninguna razón para usar la memoria del sistema o ciclos de cálculos para crearlo. Mediante el uso de `Lazy<Orders>` para declarar el objeto `Orders` para la inicialización diferida, puede evitar desperdiciar recursos del sistema si no se usa el objeto.  
  
- Cuando hay un objeto costoso de crear y quiere diferir su creación hasta después de que se hayan completado otras operaciones costosas. Por ejemplo, supongamos que el programa carga varias instancias de objeto cuando se inicia, pero solo se necesitan de inmediato algunas de ellas. Puede mejorar el rendimiento de inicio del programa si difiere la inicialización de los objetos que no son necesarios hasta que se hayan creado los objetos necesarios.  
  
 Aunque puede escribir su propio código para llevar a cabo la inicialización diferida, recomendamos que use <xref:System.Lazy%601> en su lugar. <xref:System.Lazy%601> y sus tipos relacionados también admiten la seguridad para subprocesos y ofrecen una directiva coherente de propagación de excepciones.  
  
 En la tabla siguiente se muestran los tipos que .NET Framework versión 4 proporciona para habilitar la inicialización diferida en distintos escenarios.  
  
|Tipo|Descripción|  
|----------|-----------------|  
|<xref:System.Lazy%601>|Clase contenedora que proporciona semántica de inicialización diferida para cualquier biblioteca de clases o tipo definido por el usuario.|  
|<xref:System.Threading.ThreadLocal%601>|Se parece a <xref:System.Lazy%601>, con la diferencia de que proporciona semántica de inicialización diferida para cada subproceso local. Cada subproceso tiene acceso a su propio valor único.|  
|<xref:System.Threading.LazyInitializer>|Proporciona métodos `static` avanzados (`Shared` en Visual Basic) para la inicialización diferida de objetos sin la sobrecarga de una clase.|  
  
## <a name="basic-lazy-initialization"></a>Inicialización diferida básica  
 Para definir un tipo con inicialización diferida, como `MyType`, use `Lazy<MyType>` (`Lazy(Of MyType)` en Visual Basic), como se muestra en el ejemplo siguiente. Si no se pasa ningún delegado en el constructor <xref:System.Lazy%601>, el tipo contenedor se crea mediante <xref:System.Activator.CreateInstance%2A?displayProperty=nameWithType> cuando se tiene acceso por primera vez a la propiedad de valor. Si el tipo no tiene un constructor sin parámetros, se produce una excepción en tiempo de ejecución.  
  
 En el ejemplo siguiente, supongamos que `Orders` es una clase que contiene una matriz de objetos `Order` recuperados de una base de datos. Un objeto `Customer` contiene una instancia de `Orders`, pero en función de las acciones del usuario, los datos del objeto `Orders` podrían no ser necesarios.  
  
 [!code-csharp[Lazy#1](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#1)]
 [!code-vb[Lazy#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#1)]  
  
 También se puede pasar un delegado en el constructor <xref:System.Lazy%601> que invoca una sobrecarga de constructor específica en el tipo ajustado en tiempo de creación y realizar los pasos de inicialización que se requieran, como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[Lazy#2](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#2)]
 [!code-vb[Lazy#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#2)]  
  
 Una vez que se ha creado el objeto diferido, no se crea ninguna instancia de `Orders` mientras no se tenga acceso por primera vez a la propiedad <xref:System.Lazy%601.Value%2A> de la variable Lazy. En el primer acceso, el tipo encapsulado se crea y se devuelve, y se almacena para cualquier acceso futuro.  
  
 [!code-csharp[Lazy#3](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#3)]
 [!code-vb[Lazy#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#3)]  
  
 Un objeto <xref:System.Lazy%601> siempre devuelve el mismo objeto o valor con el que se ha inicializado. Por lo tanto, la propiedad <xref:System.Lazy%601.Value%2A> es de solo lectura. Si <xref:System.Lazy%601.Value%2A> almacena un tipo de referencia, no se le puede asignar un nuevo objeto. (Sin embargo, puede cambiar el valor de sus propiedades y campos públicos configurables). Si <xref:System.Lazy%601.Value%2A> almacena un tipo de valor, no se puede modificar su valor. Aun así, puede crear una variable si invoca de nuevo el constructor de la variable con argumentos nuevos.  
  
 [!code-csharp[Lazy#4](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#4)]
 [!code-vb[Lazy#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#4)]  
  
 La nueva instancia diferida, al igual que la anterior, no crea instancias de `Orders` mientras no se tenga acceso por primera vez a su propiedad <xref:System.Lazy%601.Value%2A>.  
  
### <a name="thread-safe-initialization"></a>Inicialización segura para subprocesos  
 De forma predeterminada, los objetos <xref:System.Lazy%601> son seguros para subprocesos. Es decir, si el constructor no especifica el tipo de seguridad para subprocesos, los objetos <xref:System.Lazy%601> que crea son seguros para subprocesos. En escenarios multiproceso, el primer subproceso que tiene acceso a la propiedad <xref:System.Lazy%601.Value%2A> de un objeto <xref:System.Lazy%601> seguro para subprocesos lo inicializa para todos los accesos siguientes en todos los subprocesos, y todos los subprocesos comparten los mismos datos. Por lo tanto, no importa qué subproceso inicializa el objeto y las condiciones de carrera son benignas.  
  
> [!NOTE]
> Puede ampliar esta coherencia a las condiciones de error mediante el uso del almacenamiento en caché de excepciones. Para obtener más información, vea la próxima sección titulada [Excepciones en objetos diferidos](lazy-initialization.md#ExceptionsInLazyObjects).  
  
 En el ejemplo siguiente se muestra que la instancia `Lazy<int>` tiene el mismo valor para tres subprocesos independientes.  
  
 [!code-csharp[Lazy#8](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#8)]
 [!code-vb[Lazy#8](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#8)]  
  
 Si necesita datos independientes en cada subproceso, use el tipo <xref:System.Threading.ThreadLocal%601>, como se describe más adelante en este tema.  
  
 Algunos constructores <xref:System.Lazy%601> tienen un parámetro booleano denominado `isThreadSafe` que se usa para especificar si se obtendrá acceso a la propiedad <xref:System.Lazy%601.Value%2A> desde varios subprocesos. Si piensa tener acceso a la propiedad desde un solo subproceso, pase `false` para obtener una pequeña mejora en el rendimiento. Si piensa tener acceso a la propiedad desde varios subprocesos, pase `true` para indicarle a la instancia <xref:System.Lazy%601> que controle correctamente las condiciones de carrera en las que un subproceso produce una excepción durante la inicialización.  
  
 Algunos constructores <xref:System.Lazy%601> tienen un parámetro <xref:System.Threading.LazyThreadSafetyMode> denominado `mode`. Estos constructores proporcionan un modo adicional de seguridad para subprocesos. En la tabla siguiente se muestra la manera en que la seguridad para subprocesos de un objeto <xref:System.Lazy%601> se ve afectada por los parámetros del constructor que especifican la seguridad para subprocesos. Cada constructor tiene como máximo un parámetro de este tipo.  
  
|Seguridad para subprocesos del objeto|`LazyThreadSafetyMode``mode`parámetro de|Parámetro booleano `isThreadSafe`|Sin parámetros de seguridad para subprocesos|  
|---------------------------------|---------------------------------------------|--------------------------------------|---------------------------------|  
|Totalmente seguro para subprocesos; solo intenta inicializar el valor un subproceso de cada vez.|<xref:System.Threading.LazyThreadSafetyMode.ExecutionAndPublication>|`true`|Sí.|  
|No es seguro para subprocesos.|<xref:System.Threading.LazyThreadSafetyMode.None>|`false`|No aplicable.|  
|Totalmente seguro para subprocesos; los subprocesos se apresuran a inicializar el valor.|<xref:System.Threading.LazyThreadSafetyMode.PublicationOnly>|No aplicable.|No aplicable.|  
  
 Como se muestra en la tabla, especificar <xref:System.Threading.LazyThreadSafetyMode.ExecutionAndPublication?displayProperty=nameWithType> para el parámetro `mode` equivale a especificar `true` para el parámetro `isThreadSafe`, y especificar <xref:System.Threading.LazyThreadSafetyMode.None?displayProperty=nameWithType> equivale a especificar `false`.  
  
 Si se especifica <xref:System.Threading.LazyThreadSafetyMode.PublicationOnly?displayProperty=nameWithType>, varios subprocesos pueden intentar inicializar la instancia <xref:System.Lazy%601>. Solo un subproceso puede ganar esta carrera, y los demás subprocesos recibirán el valor que haya inicializado el subproceso ganador. Si se produce una excepción en un subproceso durante la inicialización, dicho subproceso no recibe el valor establecido por el subproceso ganador. Las excepciones no se almacenan en caché, por lo que un intento posterior para tener acceso a la propiedad <xref:System.Lazy%601.Value%2A> puede dar lugar a un inicialización correcta. Esto difiere de la manera en que se tratan las excepciones en otros modos, como se describe en la sección siguiente. Para obtener más información, vea la enumeración <xref:System.Threading.LazyThreadSafetyMode>.  
  
<a name="ExceptionsInLazyObjects"></a>
## <a name="exceptions-in-lazy-objects"></a>Excepciones en objetos diferidos  
 Como ya se ha indicado, un objeto <xref:System.Lazy%601> siempre devuelve el mismo objeto o valor con el que se ha inicializado y, por tanto, la propiedad <xref:System.Lazy%601.Value%2A> es de solo lectura. Si habilita el almacenamiento en caché de excepciones, esta inmutabilidad también se aplica al comportamiento de las excepciones. Si un objeto con inicialización diferida tiene habilitado el almacenamiento en caché de excepciones y produce una excepción desde su método de inicialización cuando <xref:System.Lazy%601.Value%2A> se obtiene acceso por primera vez a la propiedad, se produce la misma excepción en cada intento posterior de acceder a la <xref:System.Lazy%601.Value%2A> propiedad. En otras palabras, el constructor del tipo encapsulado nunca se vuelve a invocar, ni siquiera en escenarios multiproceso. Por lo tanto, el objeto <xref:System.Lazy%601> no puede producir una excepción en un acceso y devolver un valor en un acceso posterior.  
  
 El almacenamiento en caché de excepciones se habilita cuando se usa cualquier constructor <xref:System.Lazy%601?displayProperty=nameWithType> que toma un método de inicialización (un parámetro `valueFactory`); por ejemplo, se habilita cuando se usa el constructor `Lazy(T)(Func(T))`. Si el constructor también toma un valor <xref:System.Threading.LazyThreadSafetyMode> (un parámetro `mode`), especifique <xref:System.Threading.LazyThreadSafetyMode.ExecutionAndPublication?displayProperty=nameWithType> o <xref:System.Threading.LazyThreadSafetyMode.None?displayProperty=nameWithType>. Al especificar un método de inicialización, se permite el almacenamiento en caché de excepciones para estos dos modos. El método de inicialización puede ser muy simple. Por ejemplo, podría llamar al constructor sin parámetros para `T` : `new Lazy<Contents>(() => new Contents(), mode)` en C# o `New Lazy(Of Contents)(Function() New Contents())` en Visual Basic. Si usa un constructor <xref:System.Lazy%601?displayProperty=nameWithType> que no especifica un método de inicialización, las excepciones que inicie el constructor sin parámetros para `T` no se almacenarán en caché. Para obtener más información, vea la enumeración <xref:System.Threading.LazyThreadSafetyMode>.  
  
> [!NOTE]
> Si crea un objeto <xref:System.Lazy%601> con el parámetro de constructor `isThreadSafe` establecido en `false` o el parámetro de constructor `mode` establecido en <xref:System.Threading.LazyThreadSafetyMode.None?displayProperty=nameWithType>, debe tener acceso al objeto <xref:System.Lazy%601> desde un subproceso o proporcionar su propia sincronización. Esto se aplica a todos los aspectos del objeto, incluido el almacenamiento en caché de excepciones.  
  
 Como ya se ha indicado en la sección anterior, los objetos <xref:System.Lazy%601> creados al especificar <xref:System.Threading.LazyThreadSafetyMode.PublicationOnly?displayProperty=nameWithType> tratan las excepciones de forma diferente. Con <xref:System.Threading.LazyThreadSafetyMode.PublicationOnly>, varios subprocesos pueden competir para inicializar la instancia <xref:System.Lazy%601>. En este caso, las excepciones no se almacenan en caché y los intentos para obtener acceso a la propiedad <xref:System.Lazy%601.Value%2A> pueden continuar hasta que se complete la inicialización.  
  
 En la tabla siguiente se resume la forma en que los constructores <xref:System.Lazy%601> controlan el almacenamiento en caché de excepciones.  
  
|Constructor|Modo de seguridad para subprocesos|Usa método de inicialización|Las excepciones se almacenan en caché|  
|-----------------|------------------------|--------------------------------|---------------------------|  
|Lazy(T)()|(<xref:System.Threading.LazyThreadSafetyMode.ExecutionAndPublication>)|No|No|  
|Lazy(T)(Func(T))|(<xref:System.Threading.LazyThreadSafetyMode.ExecutionAndPublication>)|Sí|Sí|  
|Lazy(T)(Boolean)|`True` (<xref:System.Threading.LazyThreadSafetyMode.ExecutionAndPublication>) o `false` (<xref:System.Threading.LazyThreadSafetyMode.None>)|No|No|  
|Lazy(T)(Func(T), Boolean)|`True` (<xref:System.Threading.LazyThreadSafetyMode.ExecutionAndPublication>) o `false` (<xref:System.Threading.LazyThreadSafetyMode.None>)|Sí|Sí|  
|Lazy(T)(LazyThreadSafetyMode)|Especificado por el usuario|No|No|  
|Lazy(T)(Func(T), LazyThreadSafetyMode)|Especificado por el usuario|Sí|No si el usuario especifica <xref:System.Threading.LazyThreadSafetyMode.PublicationOnly>; en caso contrario, sí.|  
  
## <a name="implementing-a-lazy-initialized-property"></a>Implementar una propiedad con inicialización diferida  
 Para implementar una propiedad pública mediante la inicialización diferida, defina el campo de respaldo de la propiedad como <xref:System.Lazy%601> y devuelva la propiedad <xref:System.Lazy%601.Value%2A> desde el descriptor de acceso `get` de la propiedad.  
  
 [!code-csharp[Lazy#5](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#5)]
 [!code-vb[Lazy#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#5)]  
  
 La propiedad <xref:System.Lazy%601.Value%2A> es de solo lectura; por lo tanto, la propiedad que la expone no tiene ningún descriptor de acceso `set`. Si necesita una propiedad de lectura/escritura respaldada por un objeto <xref:System.Lazy%601>, el descriptor de acceso `set` debe crear un objeto <xref:System.Lazy%601> y asignarlo a la memoria auxiliar. El descriptor de acceso `set` debe crear una expresión lambda que devuelva el nuevo valor de propiedad que se ha pasado al descriptor de acceso `set` y pasar dicha expresión lambda al constructor para el nuevo objeto <xref:System.Lazy%601>. El siguiente acceso de la propiedad <xref:System.Lazy%601.Value%2A> provocará la inicialización del nuevo objeto <xref:System.Lazy%601>, y su propiedad <xref:System.Lazy%601.Value%2A> devolverá a partir de entonces el nuevo valor que se ha asignado a la propiedad. El objetivo de este complicado proceso consiste en conservar las protecciones multiproceso integradas en <xref:System.Lazy%601>. De lo contrario, los descriptores de acceso de propiedad tendrían que almacenar en caché el primer valor devuelto por la propiedad <xref:System.Lazy%601.Value%2A> y modificar solo el valor almacenado en caché, y usted tendría que escribir su propio código seguro para subprocesos para hacerlo. Debido a las inicializaciones adicionales que requiere una propiedad de lectura/escritura respaldada por un objeto <xref:System.Lazy%601>, el rendimiento podría no ser aceptable. Además, en función del escenario, podría ser necesaria una coordinación adicional para evitar condiciones de carrera entre los establecedores y los captadores.  
  
## <a name="thread-local-lazy-initialization"></a>Inicialización diferida local de subprocesos  
 En algunos escenarios multiproceso, podría interesarle asignarle a cada subproceso sus propios datos privados. Estos datos se denominan *datos locales de subproceso*. En .NET Framework versión 3.5 y anteriores, se podía aplicar el atributo `ThreadStatic` a una variable estática para convertirla en una variable local de subproceso. Pero el uso del atributo `ThreadStatic` puede producir pequeños errores. Por ejemplo, incluso las instrucciones de inicialización básicas harán que la variable solo se inicialice en el primer subproceso que tenga acceso a ella, tal como se muestra en el ejemplo siguiente.  
  
 [!code-csharp[Lazy#6](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#6)]
 [!code-vb[Lazy#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#6)]  
  
 En todos los demás subprocesos, la variable se inicializará mediante su valor predeterminado (cero). Como alternativa en .NET Framework versión 4, puede usar el tipo <xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType> para crear una variable local de subproceso basada en instancias que se inicialice en todos los subprocesos mediante el delegado <xref:System.Action%601> que proporcione. En el ejemplo siguiente, todos los subprocesos que tienen acceso a `counter` tendrán 1 como valor inicial.  
  
 [!code-csharp[Lazy#7](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#7)]
 [!code-vb[Lazy#7](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#7)]  
  
 <xref:System.Threading.ThreadLocal%601> encapsula el objeto de la misma manera que <xref:System.Lazy%601>, pero con estas diferencias básicas:  
  
- Cada subproceso inicializa la variable local de subproceso mediante sus propios datos privados, que no son accesibles desde otros subprocesos.  
  
- La propiedad <xref:System.Threading.ThreadLocal%601.Value%2A?displayProperty=nameWithType> es de lectura y escritura y se puede modificar todas las veces que se quiera. Esto puede afectar a la propagación de excepciones; por ejemplo, una operación `get` puede producir una excepción, pero la siguiente puede inicializar correctamente el valor.  
  
- Si no se proporciona ningún delegado de inicialización, <xref:System.Threading.ThreadLocal%601> inicializará su tipo encapsulado mediante el valor predeterminado del tipo. En este sentido, <xref:System.Threading.ThreadLocal%601> es coherente con el atributo <xref:System.ThreadStaticAttribute>.  
  
 En el ejemplo siguiente se muestra que cada subproceso que tiene acceso a la instancia `ThreadLocal<int>` obtiene su propia copia única de los datos.  
  
 [!code-csharp[Lazy#9](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#9)]
 [!code-vb[Lazy#9](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#9)]  
  
## <a name="thread-local-variables-in-parallelfor-and-foreach"></a>Variables locales de subproceso en Parallel.For y ForEach  
 Cuando se usa el método <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> o <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> para iterar en los orígenes de datos en paralelo, puede usar las sobrecargas que tienen compatibilidad integrada con datos locales de subproceso. En estos métodos, la localidad del subproceso se logra mediante el uso de delegados locales para crear los datos, obtener acceso a ellos y limpiarlos. Para obtener más información, vea [Cómo: Escribir un bucle Parallel.For con variables locales de subproceso](../../standard/parallel-programming/how-to-write-a-parallel-for-loop-with-thread-local-variables.md) y [How to: Write a Parallel.ForEach Loop with Thread-Local Variables](../../standard/parallel-programming/how-to-write-a-parallel-foreach-loop-with-partition-local-variables.md) (Cómo: Escribir un bucle Parallel.ForEach con variables locales de partición).  
  
## <a name="using-lazy-initialization-for-low-overhead-scenarios"></a>Usar la inicialización diferida para escenarios con poca sobrecarga  
 En los escenarios en los que tiene que inicializar de forma diferida un gran número de objetos, podría decidir que el proceso de encapsular cada objeto en un objeto <xref:System.Lazy%601> requiere demasiada memoria o demasiados recursos informáticos. O bien, es posible que tenga requisitos estrictos sobre cómo se expone la inicialización diferida. En tales casos, puede usar los métodos `static` (`Shared` en Visual Basic) de la clase <xref:System.Threading.LazyInitializer?displayProperty=nameWithType> para inicializar de forma diferida cada objeto sin encapsularlo en una instancia de <xref:System.Lazy%601>.  
  
 En el ejemplo siguiente se da por supuesto que, en lugar de encapsular todo un objeto `Orders` en un objeto <xref:System.Lazy%601>, solo se inicializan de forma diferida los objetos `Order` individuales si son necesarios.  
  
 [!code-csharp[Lazy#10](../../../samples/snippets/csharp/VS_Snippets_Misc/lazy/cs/cs_lazycodefile.cs#10)]
 [!code-vb[Lazy#10](../../../samples/snippets/visualbasic/VS_Snippets_Misc/lazy/vb/lazy_vb.vb#10)]  
  
 En este ejemplo, observe que el procedimiento de inicialización se invoca en cada iteración del bucle. En escenarios multiproceso, el primer subproceso que invoca el procedimiento de inicialización es aquel cuyo valor ven todos los subprocesos. Los subprocesos posteriores también invocan el procedimiento de inicialización, pero sus resultados no se usan. Si este tipo de condición de carrera potencial no es aceptable, use la sobrecarga de <xref:System.Threading.LazyInitializer.EnsureInitialized%2A?displayProperty=nameWithType> que toma un argumento booleano y un objeto de sincronización.  
  
## <a name="see-also"></a>Consulte también

- [Principios básicos del subprocesamiento administrado](../../standard/threading/managed-threading-basics.md)
- [Subprocesos y subprocesamiento](../../standard/threading/threads-and-threading.md)
- [Biblioteca TPL](../../standard/parallel-programming/task-parallel-library-tpl.md)
- [Procedimiento para realizar la inicialización diferida de objetos](how-to-perform-lazy-initialization-of-objects.md)
