---
title: Tiempo de inicio de una aplicación
ms.date: 03/30/2017
helpviewer_keywords:
- splash screen [WPF], startup time
- WPF [WPF], startup time
- startup time [WPF]
- application startup [WPF]
- performance [WPF], startup time
ms.assetid: f0ec58d8-626f-4d8a-9873-c20f95e08b96
ms.openlocfilehash: 0fae3ac1769163101dcdb183f4c5c2135354b1fc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145428"
---
# <a name="application-startup-time"></a>Tiempo de inicio de una aplicación
La cantidad de tiempo necesaria para iniciar una aplicación de WPF puede variar en gran medida. En este tema se describen varias técnicas para reducir el tiempo de inicio percibido y real de una aplicación de Windows Presentation Foundation (WPF).  
  
## <a name="understanding-cold-startup-and-warm-startup"></a>Comprensión del inicio en frío y del inicio en caliente  
 El inicio en frío se produce cuando la aplicación se inicia por primera vez después de un reinicio del sistema, o cuando se inicia la aplicación, se cierra y luego se inicia de nuevo después de un largo período de tiempo. Al iniciar una aplicación, si las páginas necesarias (código, datos estáticos, Registro, etc.) no se encuentran en la lista de elementos en espera del administrador de memoria de Windows, se producen errores de página. Es preciso tener acceso al disco para introducir las páginas en la memoria.  
  
 El inicio en caliente se produce cuando la mayoría de las páginas correspondientes a los principales componentes de Common Language Runtime (CLR) ya están cargadas en la memoria; esto ahorra tiempo de acceso a disco, que consume recursos. Por este motivo, una aplicación administrada se inicia más rápido cuando se ejecuta por segunda vez.  
  
## <a name="implement-a-splash-screen"></a>Implementación de una pantalla de presentación  
 En aquellos casos en que se produce un retraso significativo e inevitable desde que se inicia la aplicación hasta que se muestra la primera interfaz de usuario, es conveniente optimizar el tiempo de inicio percibido utilizando una *pantalla de presentación*. Este planteamiento consiste en mostrar una imagen casi inmediatamente en cuanto el usuario inicia la aplicación. Cuando la aplicación está lista para mostrar su primera IU, la pantalla de presentación se desvanece. A partir de .NET Framework 3.5 SP1, puede usar la <xref:System.Windows.SplashScreen> clase para implementar una pantalla de presentación. Para más información, consulte [Cómo: Agregar una pantalla de presentación a una aplicación WPF](../app-development/how-to-add-a-splash-screen-to-a-wpf-application.md).  
  
 También puede implementar su propia pantalla de presentación utilizando los gráficos nativos de Win32. Muestre la implementación antes de llamar al <xref:System.Windows.Application.Run%2A> método.  
  
## <a name="analyze-the-startup-code"></a>Análisis del código de inicio  
 Determine la razón de que el inicio en frío sea lento. Puede que se deba a la capacidad de E/S del disco, pero no siempre ocurre así. En general, es importante minimizar el uso de recursos externos, como la red, los servicios Web o el disco.  
  
 Antes de efectuar las pruebas, compruebe que no haya ninguna otra aplicación ni servicio en ejecución que utilice código administrado o código de WPF.  
  
 Inicie inmediatamente su aplicación de WPF después de un reinicio y determine cuánto tiempo tarda en mostrarse. Si todos los lanzamientos subsiguientes de su aplicación (inicio en caliente) son mucho más rápidos, lo más probable es que el problema de inicio en frío se deba a la E/S.  
  
 Si el problema de inicio en frío de la aplicación no tiene nada que ver con la E/S, lo más probable es que la aplicación lleve a cabo algún cálculo o inicialización prolongado, espere a que se complete algún evento o necesite gran cantidad de compilación JIT en el inicio. En las secciones siguientes se describen con más detalle algunas de estas situaciones.  
  
## <a name="optimize-module-loading"></a>Optimización de la carga de módulos  
 Utilice herramientas como el explorador de procesos (Procexp.exe) y Tlist.exe para determinar qué módulos carga la aplicación. El comando `Tlist <pid>` muestra todos los módulos que carga un proceso.  
  
 Por ejemplo, si no se está conectando a la web y observa que se carga System.Web.dll, significa que existe un módulo en la aplicación que hace referencia a este ensamblado. Compruebe que esta referencia sea necesaria.  
  
 Si su aplicación tiene varios módulos, combínelos en un módulo único. De este modo se consumen menos recursos de carga de ensamblados de CLR. Además, si hay menos ensamblados, CLR tendrá que mantener menos recursos.  
  
## <a name="defer-initialization-operations"></a>Diferimiento de las operaciones de inicialización  
 Estudie la posibilidad de posponer el código de inicialización hasta después de haber representado la ventana de la aplicación principal.  
  
 Tenga en cuenta que la inicialización se puede realizar dentro de un constructor de clase y que, si el código de inicialización hace referencia a otras clases, puede producir un efecto en cascada en el que se ejecuten numerosos constructores de clase.  
  
## <a name="avoid-application-configuration"></a>Evitar la configuración de la aplicación  
 Puede ser conveniente evitar la configuración de la aplicación. Por ejemplo, si los requisitos de configuración de la aplicación son sencillos y presenta objetivos de tiempo de inicio estrictos, una serie de entradas del Registro o un simple archivo INI puede ser una alternativa de inicio más rápida.  
  
## <a name="utilize-the-gac"></a>Utilización de GAC  
 Si un ensamblado no se instala en la memoria Caché global de ensamblados (GAC), se producen retrasos porque se efectúa la comprobación hash de ensamblados con nombre seguro y se lleva a cabo la validación de imagen de Ngen en caso de que haya una imagen nativa de ese ensamblado disponible en el equipo. La comprobación del nombre seguro se omite para todos los ensamblados instalados en GAC. Para más información, consulte [Gacutil.exe (Global Assembly Cache Tool)](../../tools/gacutil-exe-gac-tool.md).  
  
## <a name="use-ngenexe"></a>Uso de Ngen.exe  
 Puede ser conveniente utilizar generador de imágenes nativas (Ngen.exe) en la aplicación. Al utilizar Ngen.exe, se intercambia consumo de la CPU por más acceso al disco, porque la imagen nativa generada por Ngen.exe será, con toda probabilidad, mayor que la imagen de MSIL.  
  
 Para abreviar el tiempo de inicio en caliente, debe utilizar siempre Ngen.exe en la aplicación, ya que evita el consumo de recursos de la CPU al efectuar la compilación JIT del código de la aplicación.  
  
 En algunos escenarios de inicio en frío, también puede resultar útil el uso de Ngen.exe. Esto se debe a que se evita tener que cargar el compilador JIT (mscorjit.dll).  
  
 La presencia simultánea de módulos JIT y Ngen pueden ejercer el efecto más negativo. La causa es que hay que cargar mscorjit.dll y, cuando el compilador JIT está trabajando con el código, es preciso tener acceso a gran cantidad de páginas de las imágenes de Ngen mientras el compilador JIT lee los metadatos de los ensamblados.  
  
### <a name="ngen-and-clickonce"></a>Ngen y ClickOnce  
 La manera en que está previsto implementar la aplicación también puede marcar la diferencia en cuanto al tiempo de carga. La implementación de la aplicación ClickOnce no admite Ngen. Si decide utilizar Ngen.exe para su aplicación, tendrá que utilizar otro mecanismo de implementación, como Windows Installer.  
  
 Para obtener más información, vea el artículo sobre [Ngen.exe (generador de imágenes nativas)](../../tools/ngen-exe-native-image-generator.md).  
  
### <a name="rebasing-and-dll-address-collisions"></a>Cambios de ubicación y conflictos de direcciones de DLL  
 Si utiliza Ngen.exe, tenga en cuenta que puede producirse un cambio de ubicación al cargar en memoria las imágenes nativas. Si una DLL no se carga en su dirección base preferida porque ese intervalo de direcciones ya está asignado, el cargador de Windows la cargará en otra dirección, lo que puede consumir gran cantidad de tiempo.  
  
 Puede utilizar la herramienta Virtual Address Dump (Vadump.exe) para comprobar si existen módulos en que todas las páginas sean privadas. En caso afirmativo, puede que se haya cambiado la ubicación del módulo a otra dirección. Por consiguiente, no se pueden compartir sus páginas.  
  
 Para más información sobre cómo establecer la dirección base, consulte [Ngen.exe (Generador de imágenes nativas)](../../tools/ngen-exe-native-image-generator.md).  
  
## <a name="optimize-authenticode"></a>Optimización de Authenticode  
 La comprobación de Authenticode se suma al tiempo de inicio. Los ensamblados firmados por Authenticode tienen que comprobarse con la entidad de certificación (CA). Esta comprobación puede tardar mucho tiempo, porque es posible que haya que conectarse varias veces a la red para descargar las listas de certificados revocados actuales. También se asegura de que exista una cadena completa de certificados válidos en la ruta de acceso de una raíz confiable. Esto puede añadir varios segundos de retraso mientras se carga el ensamblado.  
  
 Puede ser interesante instalar el certificado de la entidad de certificación en el equipo cliente o evitar el uso de Authenticode siempre que sea posible. Si sabe que su aplicación no necesita la evidencia del editor, no es preciso consumir los recursos correspondientes a la comprobación de firmas.  
  
 A partir de .NET Framework 3.5, hay una opción de configuración que permite omitir la comprobación de Authenticode. Para ello, agregue el valor siguiente al archivo app.exe.config:  
  
```xml  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>
    </runtime>  
</configuration>  
```  
  
 Para obtener más información, vea [ \<generatePublisherEvidence> Element](../../configure-apps/file-schema/runtime/generatepublisherevidence-element.md).  
  
## <a name="compare-performance-on-windows-vista"></a>Comparación del rendimiento de Windows Vista  
 El administrador de memoria de Windows Vista presenta una tecnología denominada SuperFetch. SuperFetch analiza los modelos de utilización de memoria a lo largo del tiempo, a fin de determinar el contenido de la memoria óptimo para un usuario concreto. Funciona continuamente para mantener ese contenido en todo momento.  
  
 Este enfoque difiere de la técnica de captura previa utilizada en Windows XP, que carga previamente los datos en la memoria sin analizar los modelos de uso. Con el tiempo, si el usuario utiliza con frecuencia su aplicación de WPF en Windows Vista, puede suceder que mejore el tiempo del inicio en frío de esta.  
  
## <a name="use-appdomains-efficiently"></a>Utilización eficaz de AppDomains  
 Si es posible, cargue los ensamblados en un área de código neutral con respecto al dominio, para asegurarse de que se utilice la imagen nativa, si la hay, en todos los AppDomains creados en la aplicación.  
  
 Para obtener el máximo rendimiento, aplique una comunicación entre dominios eficaz reduciendo las llamadas entre dominios. Cuando sea posible, utilice llamadas sin argumentos o con argumentos de tipo primitivo.  
  
## <a name="use-the-neutralresourceslanguage-attribute"></a>Uso del atributo NeutralResourcesLanguage  
 Utilice <xref:System.Resources.NeutralResourcesLanguageAttribute> el para especificar la <xref:System.Resources.ResourceManager>referencia cultural neutra para el archivo . De este modo puede evitar búsquedas de ensamblados incorrectas.  
  
## <a name="use-the-binaryformatter-class-for-serialization"></a>Utilización de la clase BinaryFormatter para la serialización  
 Si debe usar la <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> serialización, <xref:System.Xml.Serialization.XmlSerializer> utilice la clase en lugar de la clase. La <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> clase se implementa en la biblioteca de clases base (BCL) en el ensamblado mscorlib.dll. Se <xref:System.Xml.Serialization.XmlSerializer> implementa en el ensamblado System.Xml.dll, que podría ser un archivo DLL adicional para cargar.  
  
 Si debe usar <xref:System.Xml.Serialization.XmlSerializer> la clase, puede lograr un mejor rendimiento si genera previamente el ensamblado de serialización.  
  
## <a name="configure-clickonce-to-check-for-updates-after-startup"></a>Configuración de ClickOnce para que compruebe las actualizaciones después del inicio  
 Si la aplicación usa ClickOnce, evite el acceso a la red al iniciarse configurando ClickOnce para comprobar si hay actualizaciones en el sitio de implementación después de que se inicie la aplicación.  
  
 Si usa el modelo de aplicación de explorador XAML (XBAP), tenga en cuenta que ClickOnce comprueba si hay actualizaciones en el sitio de implementación, incluso si el XBAP ya está en la caché ClickOnce. Para obtener más información, consulta [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment).  
  
## <a name="configure-the-presentationfontcache-service-to-start-automatically"></a>Configuración del servicio PresentationFontCache para que se inicie automáticamente  
 La primera aplicación de WPF que se ejecuta después de un reinicio es el servicio PresentationFontCache. El servicio almacena en memoria caché las fuentes del sistema y mejora el acceso a las fuentes, así como el rendimiento global. Iniciar el servicio consume recursos; por ello, en algunos entornos controlados puede ser conveniente configurarlo de modo que se inicie automáticamente al reiniciarse el sistema.  
  
## <a name="set-data-binding-programmatically"></a>Establecimiento del enlace de datos mediante programación  
 En lugar de usar <xref:System.Windows.FrameworkElement.DataContext%2A> XAML para establecer la declaración para la <xref:System.Windows.Application.OnActivated%2A> ventana principal, considere la posibilidad de establecerlo mediante programación en el método.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.SplashScreen>
- <xref:System.AppDomain>
- <xref:System.Resources.NeutralResourcesLanguageAttribute>
- <xref:System.Resources.ResourceManager>
- [Cómo: Agregar una pantalla de presentación a una aplicación WPF](../app-development/how-to-add-a-splash-screen-to-a-wpf-application.md)
- [Ngen.exe (Generador de imágenes nativas)](../../tools/ngen-exe-native-image-generator.md)
- [\<generatePublisherEvidence> Element](../../configure-apps/file-schema/runtime/generatepublisherevidence-element.md)
