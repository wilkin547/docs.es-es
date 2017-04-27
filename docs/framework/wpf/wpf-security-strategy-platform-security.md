---
title: "Estrategia de seguridad de WPF: Seguridad de plataforma | Microsoft Docs"
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
  - "características de seguridad de CLR"
  - "características de seguridad de Common Language Runtime (CLR)"
  - "características de seguridad de Internet Explorer"
  - "modelo de seguridad del sistema operativo"
  - "modelo de seguridad de la plataforma"
  - "modelo de seguridad"
  - "modelo de seguridad, sistema operativo"
  - "modelo de seguridad, plataforma"
  - "método crítico para la seguridad"
  - "Windows Presentation Foundation, acerca del modelo de seguridad"
  - "WPF, acerca del modelo de seguridad"
ms.assetid: 2a39a054-3e2a-4659-bcb7-8bcea490ba31
caps.latest.revision: 30
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 26
---
# Estrategia de seguridad de WPF: Seguridad de plataforma
[!INCLUDE[TLA#tla_wpf](../../../includes/tlasharptla-wpf-md.md)] proporciona una gran variedad de servicios de seguridad y, a su vez, también aprovecha las características de seguridad de la plataforma subyacente, entre las que se incluyen el sistema operativo, [!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)] e [!INCLUDE[TLA2#tla_ie](../../../includes/tla2sharptla-ie-md.md)].  Estas capas se combinan para proporcionar a [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] un modelo de seguridad sólido y profundo que intenta evitar todos los puntos flacos, como se muestra en la ilustración siguiente:  
  
 ![Ilustración de seguridad de WPF](../../../docs/framework/wpf/media/windowplatformsecurity.PNG "windowplatformsecurity")  
  
 En el resto de este tema se describen las características de cada una de estas capas que pertenecen específicamente a [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)].  
  
   
  
<a name="Operating_System_Security"></a>   
## Seguridad del sistema operativo  
 El nivel mínimo de sistema operativo requerido por [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] es [!INCLUDE[TLA2#tla_winxpsp2](../../../includes/tla2sharptla-winxpsp2-md.md)].  El núcleo de [!INCLUDE[TLA2#tla_winxpsp2](../../../includes/tla2sharptla-winxpsp2-md.md)] proporciona varias características que forman la base de seguridad de todas las aplicaciones de [!INCLUDE[TLA2#tla_win](../../../includes/tla2sharptla-win-md.md)], incluidas aquellas creadas con [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)].  [!INCLUDE[TLA#tla_longhorn](../../../includes/tlasharptla-longhorn-md.md)] incorpora las características de seguridad de [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] y las amplía.  En este tema se aborda el alcance de estas características de seguridad que son importantes para [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)], así como la integración de [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] con ellas para ofrecer una mayor defensa en profundidad.  
  
<a name="Microsoft_Windows_XP_Service_Pack_2__SP2_"></a>   
### Microsoft Windows XP Service Pack 2 \(SP2\)  
 Además de realizar un análisis y refuerzo general de [!INCLUDE[TLA2#tla_win](../../../includes/tla2sharptla-win-md.md)], en este tema estudiaremos tres características clave de [!INCLUDE[TLA2#tla_winxpsp2](../../../includes/tla2sharptla-winxpsp2-md.md)]:  
  
-   Compilación \/GS  
  
-   [!INCLUDE[TLA#tla_win_update](../../../includes/tlasharptla-win-update-md.md)].  
  
#### Compilación \/GS  
 [!INCLUDE[TLA2#tla_winxpsp2](../../../includes/tla2sharptla-winxpsp2-md.md)] proporciona protección mediante la recopilación de muchas bibliotecas de sistema principales, incluidas todas las dependencias de [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] como el [!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)], para ayudar a mitigar las saturaciones del búfer.  Esto se logra usando el parámetro \/GS con el compilador de línea de comandos de C o C\+\+.  Aunque las saturaciones del búfer se deben evitar de manera explícita, la compilación \/GS proporciona un ejemplo de una defensa en profundidad contra posibles vulnerabilidades creadas por dichas saturaciones de forma accidental o malintencionada.  
  
 Históricamente, las saturaciones del búfer han sido la causa de muchas vulnerabilidades de seguridad de gran impacto.  Una saturación del búfer se produce cuando un atacante aprovecha una vulnerabilidad de código que permite la inserción de código malintencionado que escribe más allá de los límites de un búfer.  Esto permite a un atacante secuestrar el proceso en el que se ejecuta el código; para ello, se sobrescribe la dirección de retorno de una función para que se ejecute el código del atacante.  El resultado es un código malintencionado que ejecuta código arbitrario con los mismos privilegios que el proceso atacado.  
  
 En un nivel alto, la marca del compilador \/GS protege contra algunas saturaciones del búfer potenciales mediante la inserción de una cookie de seguridad especial que protege la dirección de retorno de una función que tiene búferes de cadena locales.  Una vez que se devuelve una función, la cookie de seguridad se compara con su valor anterior.  Si el valor cambia, puede deberse a una saturación del búfer y el proceso se detiene con una condición de error.  Detener el proceso impide la ejecución de código potencialmente malintencionado.  Consulte el artículo sobre [\/GS \(comprobación de seguridad del búfer\)](https://msdn.microsoft.com/es-es/library/8dbf701c.aspx) para obtener más detalles.  
  
 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] se compila con la marca \/GS para agregar una capa más de defensa a las aplicaciones de [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)].  
  
#### Mejoras de Microsoft Windows Update  
 [!INCLUDE[TLA#tla_win_update](../../../includes/tlasharptla-win-update-md.md)] también se mejoró en [!INCLUDE[TLA2#tla_winxpsp2](../../../includes/tla2sharptla-winxpsp2-md.md)] para simplificar el proceso de descarga e instalación de actualizaciones.  Estos cambios mejoran significativamente la seguridad de clientes de [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)], ya que sirven para asegurar que sus sistemas están actualizados, especialmente en lo que se refiere a las actualizaciones de seguridad.  
  
<a name="Windows_Vista"></a>   
### Windows Vista  
 Los usuarios de [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] en [!INCLUDE[TLA#tla_longhorn](../../../includes/tlasharptla-longhorn-md.md)] se beneficiarán de las mejoras de seguridad adicionales del sistema operativo, incluidos “Acceso de usuario con privilegios mínimos”, comprobaciones de integridad de código y aislamiento de privilegios.  
  
#### Control de cuentas de usuario \[UAC\]  
 Hoy en día, los usuarios de [!INCLUDE[TLA2#tla_win](../../../includes/tla2sharptla-win-md.md)] tienden a ejecutar las aplicaciones con privilegios de administrador porque muchas requieren esos privilegios para la instalación, la ejecución o ambas.  Ser capaz de escribir la configuración predeterminada de una aplicación en el Registro es un ejemplo.  
  
 La ejecución con privilegios de administrador en realidad significa que las aplicaciones se ejecutan a partir de procesos que tienen concedidos privilegios de administrador.  El efecto de esto en la seguridad es que cualquier código malintencionado que secuestre un proceso que se ejecuta con privilegios de administrador heredará automáticamente esos privilegios, incluido el acceso a recursos críticos del sistema.  
  
 Una manera de protegerse frente a esta amenaza de seguridad es ejecutar las aplicaciones con los privilegios mínimos necesarios.  Esto se conoce como el principio de privilegios mínimos y es una característica fundamental del sistema operativo [!INCLUDE[TLA#tla_longhorn](../../../includes/tlasharptla-longhorn-md.md)].  Esta característica se denomina Control de cuentas de usuario \(UAC\) y [!INCLUDE[TLA#tla_longhorn](../../../includes/tlasharptla-longhorn-md.md)] la usa de dos maneras distintas:  
  
-   Para ejecutar la mayoría de las aplicaciones con privilegios UAC de forma predeterminada, incluso si el usuario es un administrador; solo las aplicaciones que necesitan privilegios de administrador se ejecutarán con privilegios de administrador.  Para ejecutarse con privilegios de administrador, las aplicaciones deben marcarse explícitamente en su manifiesto de aplicación o como entrada en la directiva de seguridad.  
  
-   Para proporcionar soluciones de compatibilidad como la virtualización.  Por ejemplo, muchas aplicaciones intentan escribir en ubicaciones restringidas, como C:\\Archivos de programa.  Para las aplicaciones que se ejecutan con UAC, existe una ubicación por usuario alternativa que no requiere privilegios de administrador para escribir en ella.  Para las aplicaciones que se ejecutan en UAC, UAC virtualiza C:\\Archivos de programa para que las aplicaciones que crean estar escribiendo en esa ubicación, en realidad lo estén haciendo en la ubicación por usuario alternativa.  Este tipo de trabajo de compatibilidad permite al sistema operativo ejecutar muchas aplicaciones que anteriormente no se podían ejecutar en UAC.  
  
#### Comprobaciones de integridad de código  
 [!INCLUDE[TLA#tla_longhorn](../../../includes/tlasharptla-longhorn-md.md)] incorpora comprobaciones más severas de integridad de código para evitar la inserción de código malintencionado en los archivos del sistema o en el kernel en tiempo de carga o de ejecución.  Esto va más allá de la protección de archivos de sistema.  
  
<a name="Limited_Rights_Process_for_Browser_Hosted_Applications"></a>   
### Proceso de derechos limitados para las aplicaciones hospedadas en explorador  
 Las aplicaciones de [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] hospedadas en explorador se ejecutan en el espacio aislado de la zona de Internet.  La integración de [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] con [!INCLUDE[TLA#tla_ie](../../../includes/tlasharptla-ie-md.md)] amplía esta protección con compatibilidad adicional.  
  
#### Internet Explorer 6 Service Pack 2 e Internet Explorer 7 para XP  
 [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] aprovecha la seguridad del sistema operativo mediante la limitación de privilegios de procesos para [!INCLUDE[TLA#tla_winfxwebapp#plural](../../../includes/tlasharptla-winfxwebappsharpplural-md.md)] a fin de lograr una mayor protección.  Antes de que se inicie una aplicación de [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] hospedada en explorador, el sistema operativo crea un proceso de host que quita los privilegios innecesarios del token del proceso.  Entre los privilegios que se quitan están la capacidad de apagar el equipo del usuario, la carga de controladores y el acceso de lectura a todos los archivos del equipo.  
  
#### Internet Explorer 7 para Vista  
 En [!INCLUDE[TLA#tla_ie7](../../../includes/tlasharptla-ie7-md.md)], las aplicaciones de [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] se ejecutan en modo protegido.  En concreto, las [!INCLUDE[TLA#tla_xbap#plural](../../../includes/tlasharptla-xbapsharpplural-md.md)] se ejecutan con integridad de nivel intermedio.  
  
#### Capa de defensa en profundidad  
 Puesto que las [!INCLUDE[TLA#tla_winfxwebapp#plural](../../../includes/tlasharptla-winfxwebappsharpplural-md.md)] suelen limitarse al espacio aislado establecido por el conjunto de permisos de zona de Internet, quitar estos privilegios no daña las [!INCLUDE[TLA#tla_winfxwebapp#plural](../../../includes/tlasharptla-winfxwebappsharpplural-md.md)] desde una perspectiva de compatibilidad.  En su lugar, se crea una capa adicional de defensa en profundidad; aunque una aplicación en espacio aislado sea capaz de vulnerar otras capas y secuestrar el proceso, el proceso solo tendrá privilegios limitados.  
  
 Consulte el artículo sobre el [uso de una cuenta con privilegios mínimos](http://technet.microsoft.com/library/cc700846.aspx).  
  
<a name="Common_Language_Runtime_Security"></a>   
## Seguridad de Common Language Runtime  
 [!INCLUDE[TLA#tla_clr](../../../includes/tlasharptla-clr-md.md)] ofrece varias ventajas clave de seguridad que incluyen validación y comprobación, [!INCLUDE[TLA#tla_cas](../../../includes/tlasharptla-cas-md.md)] y la metodología de seguridad crítica.  
  
<a name="Validation_and_Verification"></a>   
### Validación y comprobación  
 Para proporcionar aislamiento de ensamblados e integridad, [!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)] usa un proceso de validación.  La validación de [!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)] garantiza que los ensamblados se aíslen mediante la validación de su formato de archivo portable ejecutable \(PE\) para las direcciones que apuntan fuera del ensamblado.  La validación de [!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)] también corrobora la integridad de los metadatos que se insertan en un ensamblado.  
  
 Para garantizar la seguridad de tipos, evitar problemas de seguridad comunes \(por ejemplo,  las saturaciones del búfer\) y habilitar el espacio aislado a través de aislamiento de subprocesos, la seguridad de [!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)] usa el concepto de comprobación.  
  
 Las aplicaciones administradas se compilan en Lenguaje Intermedio de Microsoft \(MSIL\).  Cuando se ejecutan métodos en una aplicación administrada, su MSIL se compila en código nativo a través de la compilación Just\-In\-Time \(JIT\).  La compilación JIT incluye un proceso de comprobación que aplica numerosas reglas de seguridad y solidez para impedir que el código realice las siguientes acciones:  
  
-   Infringir contratos de tipo  
  
-   Introducir saturaciones del búfer  
  
-   Tener acceso descontrolado a la memoria  
  
 El código administrado que no cumple las reglas de comprobación no tiene permiso para ejecutarse, a menos que se considere código de confianza.  
  
 La ventaja que ofrece un código comprobable es una de las principales razones por las que [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] se compila en [!INCLUDE[TLA2#tla_winfx](../../../includes/tla2sharptla-winfx-md.md)].  En la medida en que se usa el código comprobable, se reduce en gran medida la posibilidad de aprovecharse de las posibles vulnerabilidades.  
  
<a name="Code_Access_Security"></a>   
### Seguridad de acceso del código  
 Una máquina cliente exhibe una amplia variedad de recursos a los que puede tener acceso una aplicación administrada, incluido el sistema de archivos, el Registro, los servicios de impresión, la interfaz de usuario, la reflexión y las variables de entorno.  Para que una aplicación administrada pueda tener acceso a cualquiera de los recursos de una máquina cliente, debe tener el permiso [!INCLUDE[TLA#tla_cas](../../../includes/tlasharptla-cas-md.md)] de [!INCLUDE[TLA2#tla_winfx](../../../includes/tla2sharptla-winfx-md.md)] para hacerlo.  Un permiso en [!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)] es una subclase de la <xref:System.Security.CodeAccessPermission>; [!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)] implementa una subclase para cada recurso al que pueden tener acceso las aplicaciones administradas.  
  
 Los permisos que [!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)] concede a una aplicación administrada cuando comienza a ejecutarse se conocen como conjunto de permisos y están determinados por la evidencia proporcionada por la aplicación.  Para las aplicaciones de [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)], la evidencia proporcionada es la ubicación —o zona— desde la que se inician las aplicaciones.  [!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)] identifica las zonas siguientes:  
  
-   **Mi PC**.  Aplicaciones iniciadas desde la máquina cliente \(de plena confianza\).  
  
-   **Intranet local**.  Aplicaciones iniciadas desde la intranet  \(de confianza parcial\).  
  
-   **Internet**.  Aplicaciones iniciadas desde Internet  \(de confianza mínima\).  
  
-   **Sitios de confianza**.  Aplicaciones identificadas por un usuario como de confianza  \(de confianza mínima\).  
  
-   **Sitios que no son de confianza**.  Aplicaciones identificadas por un usuario como no confiables  \(no confiables\).  
  
 Para cada una de estas zonas, [!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)] proporciona un conjunto de permisos predefinidos que incluye los permisos que coinciden con el nivel de confianza asociado a cada una.  Se incluyen los siguientes:  
  
-   **FullTrust**.  Para las aplicaciones iniciadas desde la zona **Mi PC**.  Se conceden todos los permisos posibles.  
  
-   **LocalIntranet**.  Para las aplicaciones iniciadas desde la zona **Intranet local**.  Un subconjunto de los permisos se concede para proporcionar acceso moderado a los recursos de una máquina cliente, incluido almacenamiento aislado, acceso sin restricciones a la interfaz de usuario, cuadros de diálogo de archivos sin restricciones, reflexión limitada y acceso limitado a las variables de entorno.  No se proporcionan permisos para los recursos críticos, como el Registro.  
  
-   **Internet**.  Para las aplicaciones iniciadas desde la zona **Internet** o **Sitios de confianza**.  Un subconjunto de los permisos se concede para proporcionar acceso limitado a los recursos de una máquina cliente, incluido almacenamiento aislado, apertura exclusiva de archivos e interfaz de usuario limitada.  En esencia, este conjunto de permisos aísla las aplicaciones de la máquina cliente.  
  
 A las aplicaciones identificadas como pertenecientes a la zona **Sitios de confianza** no se les concede ningún permiso en absoluto por parte [!INCLUDE[TLA2#tla_cas](../../../includes/tla2sharptla-cas-md.md)].  Por lo tanto, no existe un conjunto de permisos predefinidos para ellas.  
  
 La siguiente ilustración muestra la relación entre zonas, conjuntos de permisos, permisos y recursos.  
  
 ![Conjuntos de permisos CAS](../../../docs/framework/wpf/media/caspermissionsets.png "CASPermissionSets")  
  
 Las restricciones del espacio aislado de seguridad de la zona de Internet se aplican igualmente a cualquier código que un [!INCLUDE[TLA2#tla_winfxwebapp](../../../includes/tla2sharptla-winfxwebapp-md.md)] importe desde una biblioteca del sistema, incluido [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)].  Esto garantiza que cada bit del código está bloqueado, incluso [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)].  Desgraciadamente, para poder ejecutarse, un [!INCLUDE[TLA2#tla_winfxwebapp](../../../includes/tla2sharptla-winfxwebapp-md.md)] necesita ejecutar funcionalidades que requieren más permisos que los habilitados por el espacio aislado de seguridad de la zona de Internet.  
  
 Imagine una aplicación [!INCLUDE[TLA2#tla_winfxwebapp](../../../includes/tla2sharptla-winfxwebapp-md.md)] que incluya la página siguiente:  
  
 [!code-csharp[WPFPlatformSecuritySnippets#Permission](../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/CSharp/Page1.xaml.cs#permission)]
 [!code-vb[WPFPlatformSecuritySnippets#Permission](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/VisualBasic/Page1.xaml.vb#permission)]  
  
 Para ejecutar este [!INCLUDE[TLA2#tla_winfxwebapp](../../../includes/tla2sharptla-winfxwebapp-md.md)], el código [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] subyacente debe ejecutar más funcionalidad de la disponible para el [!INCLUDE[TLA2#tla_winfxwebapp](../../../includes/tla2sharptla-winfxwebapp-md.md)] de llamada, lo que incluye:  
  
-   Creación de un identificador de ventana \(hWnd\) para la representación  
  
-   Envío de mensajes  
  
-   Carga de la fuente Tahoma  
  
 Desde el un punto de vista de la seguridad, permitir el acceso directo a cualquiera de estas operaciones desde la aplicación en espacio aislado resultaría catastrófico.  
  
 Afortunadamente, [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] se encarga de esta situación ya que permite que estas operaciones se ejecuten con privilegios elevados en nombre de la aplicación en espacio aislado.  Mientras que todas las operaciones de [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] se comprueban con los permisos limitados de seguridad de la zona de Internet del dominio de [!INCLUDE[TLA2#tla_winfxwebapp](../../../includes/tla2sharptla-winfxwebapp-md.md)], a [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] \(al igual que a otras bibliotecas de sistema\) se le concede un conjunto de permisos que incluye todos los permisos posibles.  
  
 Esto requiere que [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] reciba privilegios elevados al tiempo que se evita que esos privilegios se rijan por el conjunto de permisos de zona de Internet del dominio de la aplicación host.  
  
 Para lograrlo, [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] usa el método **Assert** de un permiso.  El siguiente código muestra cómo se produce esto:  
  
 [!code-csharp[WPFPlatformSecuritySnippets#Permission](../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/CSharp/Page1.xaml.cs#permission)]
 [!code-vb[WPFPlatformSecuritySnippets#Permission](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/VisualBasic/Page1.xaml.vb#permission)]  
  
 Básicamente, **Assert** evita que los permisos ilimitados requeridos por [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] estén restringidos por los permisos de la zona de Internet de [!INCLUDE[TLA2#tla_winfxwebapp](../../../includes/tla2sharptla-winfxwebapp-md.md)].  
  
 Desde la perspectiva de plataforma, [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] es responsable de usar **Assert** correctamente; un uso incorrecto de **Assert** podría permitir que el código malintencionado elevase los privilegios.  En consecuencia, es importante llamar a **Assert** únicamente cuando sea necesario y asegurarse de que las restricciones del espacio aislado permanecen intactas.  Por ejemplo, el código en espacio aislado no tiene permiso para abrir archivos aleatorios, pero sí para usar fuentes.  [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] permite que las aplicaciones en espacio aislado usen la funcionalidad de fuentes mediante llamadas a **Assert**, y para que [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] pueda leer los archivos que contienen estas fuentes en nombre de la aplicación en espacio aislado.  
  
<a name="ClickOnce_Deployment"></a>   
### Implementación ClickOnce  
 [!INCLUDE[TLA#tla_clickonce](../../../includes/tlasharptla-clickonce-md.md)] es una completa tecnología de implementación que se incluye con [!INCLUDE[TLA2#tla_winfx](../../../includes/tla2sharptla-winfx-md.md)] y se integra con [!INCLUDE[TLA#tla_visualstu](../../../includes/tlasharptla-visualstu-md.md)] \(consulte la [información general sobre la implementación de ClickOnce](http://msdn.microsoft.com/library/142dbbz4.aspx) para obtener información detallada\).  Mientras que las aplicaciones independientes de [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] pueden implementarse de forma optativa con [!INCLUDE[TLA#tla_clickonce](../../../includes/tlasharptla-clickonce-md.md)], las aplicaciones hospedadas en explorador deben implementarse obligatoriamente con [!INCLUDE[TLA2#tla_clickonce](../../../includes/tla2sharptla-clickonce-md.md)].  
  
 Las aplicaciones implementadas mediante [!INCLUDE[TLA2#tla_clickonce](../../../includes/tla2sharptla-clickonce-md.md)] tienen una capa de seguridad adicional sobre [!INCLUDE[TLA#tla_cas](../../../includes/tlasharptla-cas-md.md)]; básicamente, las aplicaciones implementadas de [!INCLUDE[TLA#tla_clickonce](../../../includes/tlasharptla-clickonce-md.md)] solicitan los permisos que necesitan.  Esos permisos se les conceden únicamente si no exceden el conjunto de permisos para la zona desde la que se implementa la aplicación.  Al reducir el conjunto de permisos exclusivamente a los necesarios, incluso si son menores que los proporcionados por el conjunto de permisos de la zona de inicio, el número de recursos a los que tiene acceso la aplicación se reduce al mínimo necesario.  Por lo tanto, si se secuestra la aplicación, se reduce la posibilidad de daños en la máquina cliente.  
  
<a name="Security_Critical_Methodology"></a>   
### Metodología crítica para la seguridad  
 El código [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] que usa permisos para habilitar el espacio aislado de zona de Internet para las aplicaciones [!INCLUDE[TLA2#tla_winfxwebapp](../../../includes/tla2sharptla-winfxwebapp-md.md)] debe mantenerse en el máximo nivel de control y auditoría de seguridad.  Para facilitar este requisito, [!INCLUDE[TLA2#tla_winfx](../../../includes/tla2sharptla-winfx-md.md)] ofrece nueva compatibilidad para administrar el código que eleva los privilegios.  En concreto, [!INCLUDE[TLA2#tla_clr](../../../includes/tla2sharptla-clr-md.md)] permite identificar el código que eleva los privilegios y lo marca con <xref:System.Security.SecurityCriticalAttribute>; cualquier código que no esté marcado con <xref:System.Security.SecurityCriticalAttribute> se convierte en *transparente* mediante esta metodología.  Por el contrario, se impide que el código administrado que no está marcado con <xref:System.Security.SecurityCriticalAttribute> eleve sus privilegios.  
  
 La metodología crítica para la seguridad permite la organización de código [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] que eleva los privilegios en *kernel crítico para la seguridad*, siendo el resto sean transparente.  Aislar el código crítico para la seguridad permite al equipo de ingenieros de [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] centrar un control de origen y análisis de seguridad adicional en el kernel crítico para la seguridad más allá de las prácticas de seguridad estándar \(consulte la [Estrategia de seguridad de WPF: Ingeniería de seguridad](../../../docs/framework/wpf/wpf-security-strategy-security-engineering.md)\).  
  
 Tenga en cuenta que [!INCLUDE[TLA2#tla_winfx](../../../includes/tla2sharptla-winfx-md.md)] permite que el código de confianza amplíe el espacio aislado de zona de Internet de [!INCLUDE[TLA2#tla_winfxwebapp](../../../includes/tla2sharptla-winfxwebapp-md.md)] al dejar que los desarrolladores puedan escribir ensamblados administrados marcados con <xref:System.Security.AllowPartiallyTrustedCallersAttribute> \(APTCA\) e implementados en la caché global de ensamblados \(GAC\) del usuario.  Marcar un ensamblado con APTCA es una operación de seguridad muy sensible ya que permite que cualquier código llame a ese ensamblado, incluso el código malintencionado procedente de Internet.  Cuando lo haga, extreme las precauciones y siga los procedimientos recomendados; asimismo, los usuarios deben confiar en el software para que pueda instalarse.  
  
<a name="Microsoft_Internet_Explorer_Security"></a>   
## Seguridad de Microsoft Internet Explorer  
 Más allá de reducir los problemas de seguridad y simplificar la configuración de seguridad, [!INCLUDE[TLA#tla_ie6sp2](../../../includes/tlasharptla-ie6sp2-md.md)] contiene varias características que mejoran la seguridad para los usuarios de [!INCLUDE[TLA#tla_winfxwebapp#plural](../../../includes/tlasharptla-winfxwebappsharpplural-md.md)].  Estas características intentan ofrecer a los usuarios un mayor control sobre su experiencia de exploración.  
  
 En versiones previas a [!INCLUDE[TLA2#tla_ie6sp2](../../../includes/tla2sharptla-ie6sp2-md.md)], los usuarios podían experimentar lo siguiente:  
  
-   Ventanas emergentes aleatorias.  
  
-   Redirección de script confusa.  
  
-   Numerosos cuadros de diálogo de seguridad en algunos sitios web.  
  
 En algunos casos, sitios web de poca confianza trataban de engañar a los usuarios mediante la suplantación de la instalación de [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] o mostrando repetidamente un cuadro de diálogo de instalación de [!INCLUDE[TLA#tla_actx](../../../includes/tlasharptla-actx-md.md)], incluso después de que el usuario lo cancelase.  Es posible que estas técnicas indujeran a un número significativo de usuarios a tomar malas decisiones que hayan dado lugar a la instalación de aplicaciones de spyware.  
  
 [!INCLUDE[TLA2#tla_ie6sp2](../../../includes/tla2sharptla-ie6sp2-md.md)] incluye varias características para mitigar este tipo de problemas centradas en el concepto de inicio por usuario.  [!INCLUDE[TLA2#tla_ie6sp2](../../../includes/tla2sharptla-ie6sp2-md.md)] detecta si un usuario hace clic en un vínculo o elemento de la página antes de una acción, lo que se conoce como *inicio por usuario*, tratándolo de manera diferente a cuando una acción parecida se activa por el script de una página.  Por ejemplo, [!INCLUDE[TLA2#tla_ie6sp2](../../../includes/tla2sharptla-ie6sp2-md.md)] incorpora un **bloqueador de elementos emergentes** que detecta si un usuario hace clic en un botón antes de que la página cree un elemento emergente.  De este modo, [!INCLUDE[TLA2#tla_ie6sp2](../../../includes/tla2sharptla-ie6sp2-md.md)] permite la mayoría de los elementos emergentes inocuos y evita los elementos emergentes que los usuarios no solicitan ni desean.  Los elementos emergentes bloqueados se capturan en la nueva **Barra de información**, lo que permite al usuario invalidar manualmente el bloqueo y ver el elemento emergente.  
  
 La misma lógica de iniciación por usuario también se aplica a las advertencias de seguridad **Abrir**\/**Guardar**.  Los cuadros de diálogo de instalación de [!INCLUDE[TLA2#tla_actx](../../../includes/tla2sharptla-actx-md.md)] siempre se capturan en la Barra de información, a menos que representen una actualización de un control previamente instalado.  Estas medidas se combinan para brindar a los usuarios una experiencia de usuario más segura y controlada, puesto que están protegidos contra los sitios que les importunan para instalar software malintencionado o no deseado.  
  
 Estas características también protegen a los clientes que usan [!INCLUDE[TLA2#tla_ie6sp2](../../../includes/tla2sharptla-ie6sp2-md.md)] para ir a sitios web donde pueden descargar e instalar las aplicaciones de [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)].  En concreto, esto se debe a que [!INCLUDE[TLA2#tla_ie6sp2](../../../includes/tla2sharptla-ie6sp2-md.md)] ofrece una mejor experiencia de usuario que reduce la posibilidad de que los usuarios instalen aplicaciones malintencionadas o dañinas independientemente de qué tecnología se utilizó para crearlas, incluido [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)].  [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] se suma a estas protecciones usando [!INCLUDE[TLA#tla_clickonce](../../../includes/tlasharptla-clickonce-md.md)] para facilitar la descarga de sus aplicaciones a través de Internet.  Puesto que las [!INCLUDE[TLA#tla_winfxwebapp#plural](../../../includes/tlasharptla-winfxwebappsharpplural-md.md)] se ejecutan dentro de un espacio aislado de seguridad de la zona de Internet, pueden iniciarse sin problemas.  Por otro lado, las aplicaciones de [!INCLUDE[TLA2#tla_wpf](../../../includes/tla2sharptla-wpf-md.md)] independientes requieren plena confianza para ejecutarse.  Para estas aplicaciones, [!INCLUDE[TLA#tla_clickonce](../../../includes/tlasharptla-clickonce-md.md)] mostrará un cuadro de diálogo de seguridad durante el proceso de inicio a fin de notificar el uso de los requisitos de seguridad adicionales de la aplicación.  Sin embargo, esto debe ser iniciado por el usuario, se regirá por la lógica iniciada por el usuario y se puede cancelar.  
  
 [!INCLUDE[TLA2#tla_ie7](../../../includes/tla2sharptla-ie7-md.md)] incorpora y amplía las capacidades de seguridad de [!INCLUDE[TLA2#tla_ie6sp2](../../../includes/tla2sharptla-ie6sp2-md.md)] como parte de un compromiso continuo con la seguridad.  
  
## Vea también  
 [Descripción de la seguridad en Microsoft Internet Explorer 6 en Windows XP SP2](http://www.microsoft.com/downloads/details.aspx?FamilyId=E550F940-37A0-4541-B5E2-704AB386C3ED&displaylang=en)   
 [Descripción y uso del modo protegido de Internet Explorer](http://msdn.microsoft.com/library/bb250462.aspx)   
 [Windows XP Service Pack 3](http://www.microsoft.com/windows/products/windowsxp/sp3/default.mspx)   
 [Guía de seguridad de Windows Vista](http://www.microsoft.com/downloads/details.aspx?familyid=a3d1bbed-7f35-4e72-bfb5-b84a526c1565&displaylang=en)   
 [Seguridad de acceso del código](../../../docs/framework/misc/code-access-security.md)   
 [Seguridad](../../../docs/framework/wpf/security-wpf.md)   
 [Seguridad de confianza parcial de WPF](../../../docs/framework/wpf/wpf-partial-trust-security.md)   
 [Estrategia de seguridad de WPF: Ingeniería de seguridad](../../../docs/framework/wpf/wpf-security-strategy-security-engineering.md)