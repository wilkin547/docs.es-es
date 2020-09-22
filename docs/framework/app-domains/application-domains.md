---
title: Dominios de aplicación
description: Obtenga información sobre los dominios de aplicación, que proporcionan un límite de aislamiento entre aplicaciones con fines de seguridad, confiabilidad, control de versiones y descarga de ensamblados en .NET.
ms.date: 03/30/2017
helpviewer_keywords:
- process boundaries for isolation
- application isolation
- application domains, about
- common language runtime, application domains
- application domains
- runtime, application domains
- isolation between applications
- code, verification process
- verification testing code
ms.assetid: 113a8bbf-6875-4a72-a49d-ca2d92e19cc8
ms.openlocfilehash: 246566265d55a3289ef37a2987ed9c40f051e3c8
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90553374"
---
# <a name="application-domains"></a>Dominios de aplicación

Normalmente, los sistemas operativos y los entornos de Common Language Runtime proporcionan algún tipo de aislamiento entre las aplicaciones. Por ejemplo, Windows utiliza procesos para aislar las aplicaciones. Este aislamiento es necesario para garantizar que el código que se ejecuta en una aplicación no afecta negativamente a otras aplicaciones no relacionadas.  
  
 Los dominios de aplicación proporcionan un límite de aislamiento para la seguridad, confiabilidad y control de versiones, así como para descargar los ensamblados. Los dominios de aplicación suelen ser creados por hosts de motor en tiempo de ejecución, que son los responsables de arrancar automáticamente Common Language Runtime antes de que se ejecute una aplicación.  
  
## <a name="the-benefits-of-isolating-applications"></a>Ventajas de aislar aplicaciones

 Tradicionalmente se han utilizado límites de proceso para aislar las aplicaciones que se ejecutan en un mismo equipo. Cada aplicación se carga en un proceso independiente que aísla la aplicación de las demás que se estén ejecutando en el mismo equipo.  
  
 Las aplicaciones se aíslan porque las direcciones de memoria son específicas de cada proceso; un puntero de memoria pasado de un proceso a otro no se puede utilizar de ninguna manera coherente en el proceso de destino. Tampoco se pueden realizar llamadas directas entre dos procesos. En su lugar, se deben utilizar servidores proxy, que proporcionan un nivel de direccionamiento indirecto.  
  
 El código administrado debe pasar por un proceso de verificación para poder ejecutarse (a menos que el administrador haya concedido permiso para omitir la comprobación). El proceso de comprobación determina si el código puede intentar el acceso a direcciones de memoria no válidas o realizar alguna otra acción que pudiera hacer que el proceso en el que se ejecuta deje de funcionar correctamente. Cuando el código pasa la prueba de comprobación, se dice que tiene seguridad de tipos. La posibilidad de comprobar la seguridad de tipos del código permite que Common Language Runtime proporcione un gran nivel de seguridad respecto a los límites del proceso, con un costo de rendimiento mucho menor.  
  
 Los dominios de aplicación constituyen una unidad de procesamiento más segura y versátil que puede utilizar Common Language Runtime para proporcionar el aislamiento entre las aplicaciones. En un solo proceso se pueden ejecutar varios dominios de aplicación con el mismo nivel de aislamiento que existiría en procesos independientes, sin incurrir en la sobrecarga adicional que supone realizar llamadas entre procesos o cambiar de un proceso a otro. La posibilidad de ejecutar múltiples aplicaciones en un solo proceso aumenta la escalabilidad del servidor de manera importante.  
  
 Aislar las aplicaciones es también importante para la seguridad de las mismas. Por ejemplo, en un solo proceso de explorador se pueden ejecutar controles de varias aplicaciones Web de tal forma que no puedan tener acceso a los datos y recursos de los demás controles.  
  
 Éstas son las ventajas del aislamiento que ofrecen los dominios de aplicación:  
  
- Los errores de una aplicación no pueden afectar a otras aplicaciones. Debido a que el código seguro no puede generar problemas de memoria, el uso de dominios de aplicación garantiza que el código que se ejecute en un dominio no afectará a las demás aplicaciones del proceso.  
  
- Es posible detener aplicaciones concretas sin detener todo el proceso. El uso de dominios de aplicación permite descargar el código que se ejecuta en una sola aplicación.  
  
    > [!NOTE]
    > No se puede descargar ensamblados o tipos por separado. Sólo se puede descargar un dominio completo.  
  
- El código que se ejecuta en una aplicación no puede tener acceso directo al código o a los recursos de otra aplicación. Common Language Runtime impone este aislamiento al impedir que se realicen llamadas directas entre objetos de dominios de aplicación diferentes. Los objetos que se pasan entre dominios se copian o se obtiene acceso a ellos mediante proxy. Si el objeto se copia, la llamada al objeto es local. En otras palabras, el llamador y el objeto al que se hace referencia se encuentran en el mismo dominio de aplicación. Si se tiene acceso al objeto a través de un proxy, la llamada al objeto es remota. En este caso, el llamador y el objeto al que se hace referencia se encuentran en dominios de aplicación diferentes. En las llamadas entre dominios se utiliza la misma infraestructura de llamada remota que en las llamadas entre dos procesos o entre dos equipos. En consecuencia, los metadatos del objeto al que se hace referencia deben estar disponibles para ambos dominios de aplicación a fin de que la llamada al método no provoque un error en la compilación JIT. Si el dominio que llama no tiene acceso a los metadatos del objeto al que se está llamando, se podría producir un error de compilación con una excepción del tipo <xref:System.IO.FileNotFoundException>. Para obtener más información, consulta [Remote Objects](/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100)). El objeto es quien decide el mecanismo para determinar cómo se puede obtener acceso a los objetos entre dominios. Para obtener más información, vea <xref:System.MarshalByRefObject?displayProperty=nameWithType>.  
  
- La aplicación en la que se ejecuta el código establece el comportamiento del mismo. En otras palabras, el dominio de aplicación proporciona valores de configuración tales como las directivas de versión de la aplicación, la ubicación de los ensamblados remotos a los que tiene acceso e información sobre dónde encontrar los ensamblados que se cargan en el dominio.  
  
- El dominio de aplicación en el que se ejecuta el código puede controlar los permisos que se conceden al código.  
  
## <a name="application-domains-and-assemblies"></a>Dominios de aplicación y ensamblados

 En esta sección se describe la relación entre los dominios de aplicación y los ensamblados. Debe cargar un ensamblado en un dominio de aplicación para poder ejecutar el código que contiene. Al ejecutar una aplicación típica, se cargan varios ensamblados en un dominio de aplicación.  
  
 El modo en que se carga un ensamblado determina si varios dominios de aplicación pueden compartir el código compilado Just-in-time (JIT) del ensamblado en el proceso y si el ensamblado se puede descargar del proceso.  
  
- Si un ensamblado se carga con dominio neutro, todos los dominios de aplicación que comparten el mismo conjunto de permisos de seguridad pueden compartir el mismo código compilado JIT, lo que reduce la cantidad de memoria que necesita la aplicación. Sin embargo, el ensamblado nunca se puede descargar del proceso.  
  
- Si un ensamblado no se carga con dominio neutro, debe utilizarse la compilación JIT de ese ensamblado en los dominios de aplicación en que se carga. Sin embargo, el ensamblado se puede descargar del proceso; para ello, tendrán que descargarse todos los dominios de aplicación en que está cargado el ensamblado.  
  
 El host en tiempo de ejecución determina si los ensamblados se cargan con dominio neutro cuando se carga el motor en tiempo de ejecución en un proceso. En las aplicaciones administradas, aplique el atributo <xref:System.LoaderOptimizationAttribute> al método de punto de entrada del proceso y especifique un valor de la enumeración <xref:System.LoaderOptimization> asociada. En las aplicaciones no administradas que hospedan Common Language Runtime, especifique el marcador adecuado cuando llame al método [CorBindToRuntimeEx Function](../unmanaged-api/hosting/corbindtoruntimeex-function.md).  
  
 Existen tres opciones para cargar ensamblados neutrales respecto al dominio:  
  
- <xref:System.LoaderOptimization.SingleDomain?displayProperty=nameWithType> no carga ensamblados con dominio neutro, a excepción de Mscorlib que siempre se carga con dominio neutro. Esta configuración se denomina dominio simple porque suele utilizarse cuando el host ejecuta una sola aplicación en el proceso.

- <xref:System.LoaderOptimization.MultiDomain?displayProperty=nameWithType> carga todos los ensamblados con dominio neutro. Use esta configuración cuando en el proceso haya varios dominios de aplicación que ejecutan el mismo código.

- <xref:System.LoaderOptimization.MultiDomainHost?displayProperty=nameWithType> carga con dominio neutro los ensamblados que tienen un nombre seguro si se han instalado junto con todas sus dependencias en la caché global de ensamblados. La carga y la compilación JIT de los demás ensamblados se realiza de forma independiente en cada dominio de aplicación y, por tanto, estos ensamblados pueden descargarse del proceso. Utilice esta configuración cuando ejecute más de una aplicación en el mismo proceso, o si tiene un grupo heterogéneo de ensamblados compartidos por varios dominios de aplicación y ensamblados que es necesario descargar del proceso.
  
 El código compilado JIT no se puede compartir en los ensamblados que se cargan en la carga de ensamblado por contexto especificado por el usuario utilizando el método <xref:System.Reflection.Assembly.LoadFrom%2A> de la clase <xref:System.Reflection.Assembly>, o que se cargan a partir de imágenes que utilizan las sobrecargas del método <xref:System.Reflection.Assembly.Load%2A> que especifican matrices de bytes.  
  
 Los ensamblados que se han compilado en código nativo utilizando [Ngen.exe (Native Image Generator )](../tools/ngen-exe-native-image-generator.md) se pueden compartir entre dominios de aplicación si la primera vez que se cargaron en un proceso lo hicieron con dominio neutro.  
  
 El código compilado JIT del ensamblado que contiene el punto de entrada de la aplicación sólo se puede compartir si pueden hacerlo todas sus dependencias.  
  
 Un ensamblado con dominio neutro puede someterse a la compilación JIT varias veces. Por ejemplo, cuando los conjuntos de permisos de seguridad de dos dominios de aplicación son diferentes, no pueden compartir el mismo código compilado JIT. Sin embargo, cada copia del ensamblado objeto de compilación JIT se puede compartir con otros dominios de aplicación que tengan el mismo conjunto de permisos de seguridad.  
  
 A la hora de determinar si va a cargar los ensamblados con dominio neutro, deberá decidir si prefiere reducir el consumo de memoria u otros factores relativos al rendimiento.  
  
- El acceso a los métodos y datos estáticos es más lento en los ensamblados de dominio neutro porque es necesario aislar los ensamblados. Cada dominio de aplicación que tiene acceso al ensamblado debe disponer de una copia independiente de los datos estáticos para impedir que las referencias a objetos en los campos estáticos atraviesen los límites del dominio. Como resultado, el motor en tiempo de ejecución contiene lógica adicional para dirigir un llamador a la copia correspondiente del método o los datos estáticos. Esta lógica adicional retarda la llamada.  
  
- Todas las dependencias de un ensamblado deben estar presentes y cargarse cuando el ensamblado se carga con dominio neutro, ya que si una dependencia no se puede cargar con dominio neutro, impedirá también que el ensamblado se cargue con dominio neutro.  
  
## <a name="application-domains-and-threads"></a>Dominios de aplicación y subprocesos

 Un dominio de aplicación constituye un límite de aislamiento para la seguridad, el control de versiones, la confiabilidad y la descarga de código administrado. Los subprocesos son la construcción del sistema operativo que Common Language Runtime utiliza para ejecutar código. En tiempo de ejecución, todo el código administrado se carga en un dominio de aplicación y se ejecuta mediante uno o varios subprocesos administrados.  
  
 No existe una correlación uno a uno entre los dominios de aplicación y los subprocesos. En un momento dado haber varios subprocesos ejecutándose en un único dominio de aplicación. Además, cada subproceso concreto no está confinado a un solo dominio de aplicación. En otras palabras, los subprocesos pueden cruzar los límites del dominio de aplicación; no se crea un nuevo subproceso para cada dominio de aplicación.  
  
 En un momento dado, todos los subprocesos se ejecutan en un dominio de aplicación. Por tanto, podría haber cero, uno o varios subprocesos ejecutándose en un dominio de aplicación determinado. El entorno de ejecución realiza un seguimiento de qué subprocesos se están ejecutando en qué dominios de aplicación. Se puede localizar en cualquier momento el dominio donde se está ejecutando un subproceso llamando al método <xref:System.Threading.Thread.GetDomain%2A?displayProperty=nameWithType>.

### <a name="application-domains-and-cultures"></a>Dominios de aplicación y referencias culturales

 La referencia cultural, representada por un objeto <xref:System.Globalization.CultureInfo>, se asocia con subprocesos. Puede obtener la referencia cultural asociada al subproceso que está actualmente en ejecución utilizando la propiedad <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>, y puede utilizar la propiedad <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> para obtener o establecer la referencia cultural asociada al subproceso que está actualmente en ejecución. Si la referencia cultural asociada a un subproceso se ha establecido explícitamente mediante la propiedad <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType>, seguirá asociada a ese subproceso cuando el subproceso cruce los límites del dominio de aplicación. De lo contrario, la referencia cultural que estaba asociada al subproceso en un momento concreto vendrá determinada por el valor de la propiedad <xref:System.Globalization.CultureInfo.DefaultThreadCurrentCulture%2A?displayProperty=nameWithType> en el dominio de aplicación en el que se está ejecutando el subproceso:  
  
- Si el valor de la propiedad no es `null`, se asociará al subproceso la referencia cultural devuelta por la propiedad (y por consiguiente devuelta por las propiedades <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> y <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=nameWithType>).  
  
- Si el valor de la propiedad es `null`, se asociará al subproceso la referencia cultural actual del sistema.  
  
## <a name="programming-with-application-domains"></a>Programación con dominios de aplicación

 Normalmente, los dominios de aplicación son creados y manipulados mediante programación por los hosts de motor en tiempo de ejecución. Sin embargo, a veces, puede darse la circunstancia de que un programa de aplicación deba trabajar con dominios de aplicación. Por ejemplo, un programa de aplicación podría cargar un componente de aplicación en un dominio para poder descargar el dominio (y el componente) sin necesidad de detener toda la aplicación.  
  
 La <xref:System.AppDomain> es la interfaz de programación para los dominios de aplicación. Esta clase incluye métodos para crear y descargar dominios, crear instancias de tipos en dominios y registrar diversas notificaciones, como por ejemplo cuando una aplicación descarga un dominio. En la tabla siguiente, se presentan los métodos <xref:System.AppDomain> más usados.  
  
|Método de AppDomain|Descripción|  
|----------------------|-----------------|  
|<xref:System.AppDomain.CreateDomain%2A>|Crea un nuevo dominio de aplicación. Se recomienda utilizar una sobrecarga de este método que especifique un objeto <xref:System.AppDomainSetup>. Ésta es la forma recomendada para establecer las propiedades de un nuevo dominio, como la base de la aplicación o el directorio raíz para la aplicación; la ubicación del archivo de configuración para el dominio; y la ruta de búsqueda que va a utilizar Common Language Runtime para cargar ensamblados en el dominio.|  
|<xref:System.AppDomain.ExecuteAssembly%2A> y <xref:System.AppDomain.ExecuteAssemblyByName%2A>|Ejecuta un ensamblado en el dominio de aplicación. Éste es un método de instancia, por lo que se puede utilizar para ejecutar el código en otro dominio de aplicación al que se haga referencia.|  
|<xref:System.AppDomain.CreateInstanceAndUnwrap%2A>|Crea una instancia de un tipo especificado en el dominio de aplicación y devuelve un proxy. Utilice este método para evitar que se cargue el ensamblado que contiene el tipo creado en el ensamblado de llamada.|  
|<xref:System.AppDomain.Unload%2A>|Cierra el dominio correctamente. El dominio de aplicación no se descarga hasta que todos los subprocesos que se están ejecutando en el dominio se hayan detenido o ya no se encuentren en el dominio.|  
  
> [!NOTE]
> Common Language Runtime no admite la serialización de métodos globales, por lo que no se pueden utilizar los delegados para ejecutar métodos globales en otros dominios de aplicación.  
  
 Las interfaces no administradas que se describen en la especificación de las interfaces de hospedaje de Common Language Runtime también proporcionan acceso a los dominios de aplicación. Los hosts de motor en tiempo de ejecución pueden usar interfaces de código no administrado para crear y obtener acceso a los dominios de aplicación en un proceso.  
  
## <a name="the-complus_loaderoptimization-environment-variable"></a>COMPLUS_LoaderOptimization (Variable de entorno)

 Variable de entorno que establece la directiva predeterminada de optimización de cargador de una aplicación ejecutable.  
  
### <a name="syntax"></a>Sintaxis  
  
```env  
COMPLUS_LoaderOptimization = 1  
```  
  
### <a name="remarks"></a>Comentarios

 Una aplicación típica carga varios ensamblados en un dominio de aplicación antes de poder ejecutar el código que contienen.  
  
 La manera en que se carga el ensamblado determina si su código compilado Just-In-Time (JIT) se puede compartir entre varios dominios de aplicación del proceso.  
  
- Si un ensamblado se carga con dominio neutro, todos los dominios de aplicación que comparten el mismo conjunto de permisos de seguridad pueden compartir el mismo código compilado JIT. Esto reduce la cantidad de memoria que necesita la aplicación.  
  
- Si un ensamblado no se carga con dominio neutro, debe someterse a la compilación JIT en cada dominio de aplicación en el que se carga y el cargador no debe compartir recursos internos entre dominios de aplicación.  
  
 Cuando se establece en 1, la marca de entorno COMPLUS_LoaderOptimization obliga al host del runtime a cargar todos los ensamblados de una manera no neutra para el dominio que se conoce como SingleDomain. SingleDomain no carga ensamblados con dominio neutro, a excepción de Mscorlib, que siempre se carga con dominio neutro. Esta configuración se denomina dominio simple porque suele utilizarse cuando el host ejecuta una sola aplicación en el proceso.  
  
> [!CAUTION]
> La marca de entorno COMPLUS_LoaderOptimization se diseñó para utilizarse en escenarios de diagnóstico y prueba. Tener la marca activada puede producir una considerable ralentización y un aumento del uso de memoria.  
  
### <a name="code-example"></a>Ejemplo de código

 Si anexa `COMPLUS_LoaderOptimization=1` en el valor de cadena múltiple del entorno de la clave HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\services\IISADMIN, podrá conseguir que no todos los ensamblados se carguen como dominio neutro para el servicio IISADMIN.  
  
```env  
Key = HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\services\IISADMIN  
Name = Environment  
Type = REG_MULTI_SZ  
Value (to append) = COMPLUS_LoaderOptimization=1  
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.AppDomain?displayProperty=nameWithType>
- <xref:System.MarshalByRefObject?displayProperty=nameWithType>
- [Programación con dominios de aplicación y ensamblados](index.md)
- [Utilizar dominios de aplicación](use.md)
