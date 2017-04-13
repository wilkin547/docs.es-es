---
title: "Tiempo de inicio de una aplicaci&#243;n | Microsoft Docs"
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
  - "inicio de la aplicación [WPF]"
  - "rendimiento [WPF], tiempo de inicio"
  - "pantalla de presentación [WPF], tiempo de inicio"
  - "tiempo de inicio [WPF]"
  - "WPF, tiempo de inicio"
ms.assetid: f0ec58d8-626f-4d8a-9873-c20f95e08b96
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# Tiempo de inicio de una aplicaci&#243;n
La cantidad de tiempo necesaria para iniciar una aplicación de WPF puede variar en gran medida.  En este tema se describen varias técnicas para reducir el tiempo de inicio percibido y real de una aplicación de Windows Presentation Foundation \(WPF\).  
  
## Entender inicio en frío y el inicio en caliente  
 El inicio en frío se produce cuando la aplicación se inicia por primera vez después de un reinicio del sistema, o cuando se inicia la aplicación, se cierra y, a continuación, se inicia de nuevo después de un largo período de tiempo.  Al iniciar una aplicación, si las páginas necesarias \(código, datos estáticos, Registro, etc.\) no se encuentran en la lista de elementos en espera del administrador de memoria de Windows, se producen errores de página.  Es preciso tener acceso al disco para introducir las páginas en la memoria.  
  
 El inicio en caliente se produce cuando la mayoría de las páginas correspondientes a los principales componentes de Common Language Runtime \(CLR\) ya están cargadas en la memoria; esto ahorra tiempo de acceso a disco, que consume recursos.  Por este motivo, una aplicación administrada se inicia antes cuando se ejecuta por segunda vez.  
  
## Implementar una pantalla de presentación  
 En aquellos casos en que se produce un retraso significativo e inevitable desde que se inicia la aplicación hasta que se muestra la primera interfaz de usuario, es conveniente optimizar el tiempo de inicio percibido utilizando una *pantalla de presentación*.  Este planteamiento consiste en mostrar una imagen casi inmediatamente en cuanto el usuario inicia la aplicación.  Cuando la aplicación está lista para mostrar su primera interfaz de usuario, la pantalla de presentación se desvanece.  A partir de [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)], puede utilizar la clase <xref:System.Windows.SplashScreen> para implementar una pantalla de presentación.  Para obtener más información, vea [Agregar una pantalla de presentación a una aplicación WPF](../../../../docs/framework/wpf/app-development/how-to-add-a-splash-screen-to-a-wpf-application.md).  
  
 También puede implementar su propia pantalla de presentación utilizando los gráficos nativos de Win32.  Muestre su implementación antes de que se llame al método <xref:System.Windows.Application.Run%2A>.  
  
## Analizar el código de inicio  
 Determine la razón de que el inicio en frío sea lento.  Puede que se deba a la capacidad de E\/S del disco, pero no siempre ocurre así.  En general, es importante minimizar el uso de recursos externos, como la red, los servicios Web o el disco.  
  
 Antes de efectuar las pruebas, compruebe que no haya ninguna otra aplicación ni servicio en ejecución que utilice código administrado o código de WPF.  
  
 Inicie inmediatamente su aplicación de WPF después de un reinicio y determine cuánto tiempo tarda en mostrarse.  Si todos los lanzamientos subsiguientes de su aplicación \(inicio en caliente\) son mucho más rápidos, lo más probable es que el problema de inicio en frío se deba a la capacidad de E\/S.  
  
 Si el problema de inicio en frío de la aplicación no tiene nada que ver con la capacidad de E\/S, lo más probable es que la aplicación lleve a cabo algún cálculo o inicialización prolongado, espere a que se complete algún evento o necesite gran cantidad de compilación JIT en el inicio.  En las secciones siguientes se describen con más detalle algunas de estas situaciones.  
  
## Optimizar la carga de módulos  
 Utilice herramientas como el explorador de procesos \(Procexp.exe\) y Tlist.exe para determinar qué módulos carga la aplicación.  El comando `Tlist <pid>` muestra todos los módulos que carga un proceso.  
  
 Por ejemplo, si no está conectando a la web y observa que se carga System.Web.dll, significa que existe un módulo en la aplicación que hace referencia a este ensamblado.  Compruebe que esta referencia sea necesaria.  
  
 Si su aplicación tiene varios módulos, combínelos en un módulo único.  De este modo se consumen menos recursos de carga de ensamblados de CLR.  Además, si hay menos ensamblados, CLR tendrá que mantener menos recursos.  
  
## Diferir las operaciones de inicialización  
 Estudie la posibilidad de posponer el código de inicialización hasta después de haber representado la ventana de la aplicación principal.  
  
 Tenga en cuenta que la inicialización se puede realizar dentro de un constructor de clase y que, si el código de inicialización hace referencia a otras clases, puede producir un efecto en cascada en el que se ejecuten numerosos constructores de clase.  
  
## Evitar la configuración de la aplicación  
 Puede ser conveniente evitar la configuración de la aplicación.  Por ejemplo, si los requisitos de configuración de la aplicación son sencillos y presenta objetivos de tiempo de inicio estrictos, una serie de entradas del Registro o un simple archivo INI pueden ser una alternativa de inicio más rápida.  
  
## Utilizar la GAC  
 Si un ensamblado no se instala en la memoria Caché global de ensamblados \(GAC\), se producen retrasos porque se efectúa la comprobación hash de ensamblados con nombre seguro y se lleva a cabo la validación de imagen de Ngen en caso de que haya una imagen nativa de ese ensamblado disponible en el equipo.  La comprobación del nombre seguro se omite para todos los ensamblados instalados en la GAC.  Para obtener más información, vea [Gacutil.exe \(Herramienta Caché global de ensamblados\)](../../../../docs/framework/tools/gacutil-exe-gac-tool.md).  
  
## Utilizar Ngen.exe  
 Puede ser conveniente utilizar generador de imágenes nativas \(Ngen.exe\) en la aplicación.  Al utilizar Ngen.exe, se intercambia consumo de la CPU por más acceso al disco, porque la imagen nativa generada por Ngen.exe será, con toda probabilidad, mayor que la imagen de MSIL.  
  
 Para abreviar el tiempo de inicio en caliente, debe utilizar siempre Ngen.exe en la aplicación, ya que evita el consumo de recursos de la CPU al efectuar la compilación JIT del código de la aplicación.  
  
 En algunos escenarios de inicio en frío, también puede resultar útil el uso de Ngen.exe.  Esto se debe a que se evita tener que cargar el compilador JIT \(mscorjit.dll\).  
  
 La presencia simultánea de módulos JIT y Ngen pueden ejercer el efecto más negativo.  La causa es que hay que cargar mscorjit.dll y, cuando el compilador JIT está trabajando con el código, es preciso tener acceso a gran cantidad de páginas de las imágenes de Ngen mientras el compilador JIT lee los metadatos de los ensamblados.  
  
### Ngen y ClickOnce  
 La manera en que está previsto implementar la aplicación también puede marcar la diferencia en cuanto al tiempo de la carga.  La implementación de aplicaciones de [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] no admite Ngen.  Si decide utilizar Ngen.exe para su aplicación, tendrá que utilizar otro mecanismo de distribución, como Windows Installer.  
  
 Para obtener más información, vea [Ngen.exe \(Generador de imágenes nativas\)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).  
  
### Cambios de ubicación y conflictos de direcciones de DLL  
 Si utiliza Ngen.exe, tenga en cuenta que puede producirse un cambio de ubicación al cargar en memoria las imágenes nativas.  Si una DLL no se carga en su dirección base preferida porque ese intervalo de direcciones ya está asignado, el cargador de Windows la cargará en otra dirección, lo que puede consumir gran cantidad de tiempo.  
  
 Puede utilizar la herramienta Virtual Address Dump \(Vadump.exe\) para comprobar si existen módulos en que todas las páginas sean privadas.  En caso afirmativo, puede que se haya cambiado la ubicación del módulo a otra dirección.  Por consiguiente, no se pueden compartir sus páginas.  
  
 Para obtener más información sobre cómo establecer la dirección base, vea [Ngen.exe \(Generador de imágenes nativas\)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).  
  
## Optimizar Authenticode  
 La comprobación de Authenticode se suma al tiempo de inicio.  Los ensamblados firmados por Authenticode tienen que comprobarse con la entidad de certificación \(CA\).  Esta comprobación puede tardar mucho tiempo, porque es posible que haya que conectarse varias veces a la red para descargar las listas de certificados revocados actuales.  También se asegura de que exista una cadena completa de certificados válidos en la ruta de acceso de una raíz confiable.  Esto puede añadir varios segundos de retraso mientras se carga el ensamblado.  
  
 Puede ser interesante instalar el certificado de la entidad de certificación en el equipo cliente o evitar el uso de Authenticode siempre que sea posible.  Si sabe que su aplicación no necesita la evidencia del editor, no es preciso consumir los recursos correspondientes a la comprobación de firmas.  
  
 A partir de [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)], existe una opción de configuración que permite omitir la comprobación de Authenticode.  Para ello, agregue el valor siguiente al archivo app.exe.config:  
  
```  
<configuration>  
    <runtime>  
        <generatePublisherEvidence enabled="false"/>   
    </runtime>  
</configuration>  
```  
  
 Para obtener más información, vea [\<generatePublisherEvidence\> \(Elemento\)](../../../../docs/framework/configure-apps/file-schema/runtime/generatepublisherevidence-element.md).  
  
## Comparar el rendimiento en Windows Vista  
 El administrador de memoria de Windows Vista presenta una tecnología denominada SuperFetch.  SuperFetch analiza los modelos de utilización de memoria a lo largo del tiempo, a fin de determinar el contenido de la memoria óptimo para un usuario concreto.  Funciona continuamente para mantener ese contenido en todo momento.  
  
 Este enfoque difiere de la técnica de captura previa utilizada en Windows XP, que carga previamente los datos en la memoria sin analizar los modelos de uso.  Con el tiempo, si el usuario utiliza con frecuencia su aplicación de WPF en Windows Vista, puede suceder que mejore el tiempo del inicio en frío de ésta.  
  
## Utilizar eficazmente AppDomains  
 Si es posible, cargue los ensamblados en un área de código neutral con respecto al dominio, para asegurarse de que se utilice la imagen nativa, si la hay, en todos los AppDomains creados en la aplicación.  
  
 Para obtener el máximo rendimiento, aplique una comunicación entre dominios eficaz reduciendo las llamadas entre dominios.  Cuando sea posible, utilice llamadas sin argumentos o con argumentos de tipo primitivo.  
  
## Utilizar el atributo NeutralResourcesLanguage  
 Utilice el atributo <xref:System.Resources.NeutralResourcesLanguageAttribute> para especificar la referencia cultural neutra para el objeto <xref:System.Resources.ResourceManager>.  De este modo puede evitar búsquedas de ensamblados incorrectas.  
  
## Utilizar la clase BinaryFormatter para la serialización  
 Si tiene que utilizar la serialización, utilice la clase <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> en lugar de la clase <xref:System.Xml.Serialization.XmlSerializer>.  La clase <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> se implementa en la biblioteca de clases base \(BCL\), en el ensamblado mscorlib.dll.  <xref:System.Xml.Serialization.XmlSerializer> se implementa en el ensamblado System.Xml.dll, que puede ser una DLL adicional que habrá que cargar.  
  
 Si tiene que utilizar la clase <xref:System.Xml.Serialization.XmlSerializer>, puede mejorar el rendimiento generando previamente el ensamblado de serialización.  
  
## Configurar ClickOnce para que compruebe las actualizaciones después del inicio  
 Si la aplicación utiliza [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)], evite el acceso de red durante el inicio configurando [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] de modo que compruebe si hay actualizaciones en el sitio de implementación después de que se haya iniciado la aplicación.  
  
 Si utiliza el modelo de aplicación de explorador XAML \(XBAP\), tenga presente que [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)] comprueba si hay actualizaciones en el sitio de implementación aunque la XBAP ya esté en la memoria caché de [!INCLUDE[ndptecclick](../../../../includes/ndptecclick-md.md)].  Para obtener más información, vea [Seguridad e implementación ClickOnce](../Topic/ClickOnce%20Security%20and%20Deployment.md).  
  
## Configurar el servicio PresentationFontCache para que se inicie automáticamente  
 La primera aplicación de WPF que se ejecuta después de un reinicio es el servicio PresentationFontCache.  El servicio almacena en memoria caché las fuentes del sistema y mejora el acceso a las fuentes, así como el rendimiento global.  Iniciar el servicio consume recursos; por ello, en algunos entornos controlados puede ser conveniente configurarlo de modo que se inicie automáticamente al reiniciarse el sistema.  
  
## Establecer el enlace de datos mediante programación  
 En lugar de utilizar XAML para establecer mediante declaración la propiedad <xref:System.Windows.FrameworkElement.DataContext%2A> correspondiente a la ventana principal, puede ser interesante establecerla mediante programación en el método <xref:System.Windows.Application.OnActivated%2A>.  
  
## Vea también  
 <xref:System.Windows.SplashScreen>   
 <xref:System.AppDomain>   
 <xref:System.Resources.NeutralResourcesLanguageAttribute>   
 <xref:System.Resources.ResourceManager>   
 [Agregar una pantalla de presentación a una aplicación WPF](../../../../docs/framework/wpf/app-development/how-to-add-a-splash-screen-to-a-wpf-application.md)   
 [Ngen.exe \(Generador de imágenes nativas\)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md)   
 [\<generatePublisherEvidence\> \(Elemento\)](../../../../docs/framework/configure-apps/file-schema/runtime/generatepublisherevidence-element.md)