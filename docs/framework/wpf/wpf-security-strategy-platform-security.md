---
title: Estrategia de seguridad de la plataforma
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- platform security model [WPF]
- Common Language Runtime (CLR) security features
- operating system security model [WPF]
- Internet Explorer security features [WPF]
- Security-Critical method
- CLR security features [WPF]
- security model [WPF]
- security model [WPF], platform
- WPF [WPF], about security model
- Windows Presentation Foundation [WPF], about security model
- security model [WPF], operating system
ms.assetid: 2a39a054-3e2a-4659-bcb7-8bcea490ba31
ms.openlocfilehash: 258fcd7c51ea59de03fe60a4eeb9a82dd1c7efca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174607"
---
# <a name="wpf-security-strategy---platform-security"></a>Estrategia de seguridad de WPF: Seguridad de plataforma
Aunque Windows Presentation Foundation (WPF)Windows Presentation Foundation (WPF) proporciona una variedad de servicios de seguridad, también aprovecha las características de seguridad de la plataforma subyacente, que incluye el sistema operativo, CLR e Internet Explorer. Estas capas se combinan para proporcionar a WPFWPF un modelo de seguridad fuerte y de defensa en profundidad que intenta evitar cualquier punto único de error, como se muestra en la figura siguiente:  
  
 ![Diagrama que muestra el modelo de seguridad WPFWPF.](./media/wpf-security-strategy-platform-security/windows-presentation-foundation-security.png)  
  
 En el resto de este tema se describen las características de cada una de estas capas que pertenecen específicamente a WPFWPF.  

## <a name="operating-system-security"></a>Seguridad del sistema operativo  
El núcleo de Windows proporciona varias características de seguridad que forman la base de seguridad para todas las aplicaciones de Windows, incluidas las creadas con WPFWPF. En este tema se describe la amplitud de estas características de seguridad que son importantes para WPFWPF, así como cómo WPFWPF se integra con ellos para proporcionar más defensa en profundidad.  
  
### <a name="microsoft-windows-xp-service-pack-2-sp2"></a>Microsoft Windows XP Service Pack 2 (SP2)  
 Además de una revisión general y el fortalecimiento de Windows, hay tres características clave de Windows XP SP2 que discutiremos en este tema:  
  
- Compilación /GS  
  
- Actualización de Microsoft Windows.  
  
#### <a name="gs-compilation"></a>Compilación /GS  
 Windows XP SP2 proporciona protección al volver a compilar muchas bibliotecas principales del sistema, incluidas todas las dependencias de WPFWPF, como CLR, para ayudar a mitigar las saturaciones de búfer. Esto se logra usando el parámetro /GS con el compilador de línea de comandos de C o C++. Aunque las saturaciones del búfer se deben evitar de manera explícita, la compilación /GS proporciona un ejemplo de una defensa en profundidad contra posibles vulnerabilidades creadas por dichas saturaciones de forma accidental o malintencionada.  
  
 Históricamente, las saturaciones del búfer han sido la causa de muchas vulnerabilidades de seguridad de gran impacto. Una saturación del búfer se produce cuando un atacante aprovecha una vulnerabilidad de código que permite la inserción de código malintencionado que escribe más allá de los límites de un búfer. Esto permite a un atacante secuestrar el proceso en el que se ejecuta el código; para ello, se sobrescribe la dirección de retorno de una función para que se ejecute el código del atacante. El resultado es un código malintencionado que ejecuta código arbitrario con los mismos privilegios que el proceso atacado.  
  
 En un nivel alto, el indicador del compilador -GS protege contra algunas saturaciones de búfer potenciales mediante la inserción de una cookie de seguridad especial para proteger la dirección de retorno de una función que tiene búferes de cadena locales. Una vez que se devuelve una función, la cookie de seguridad se compara con su valor anterior. Si el valor cambia, puede deberse a una saturación del búfer y el proceso se detiene con una condición de error. Detener el proceso impide la ejecución de código potencialmente malintencionado. Consulte [-GS (Comprobación](/cpp/build/reference/gs-buffer-security-check) de seguridad de búfer) para obtener más detalles.  
  
 WPFWPF se compila con la marca /GS para agregar otra capa de defensa a las aplicaciones WPFWPF.  
  
### <a name="windows-vista"></a>Windows Vista  
Los usuarios de WPF en Windows Vista se beneficiarán de las mejoras de seguridad adicionales del sistema operativo, como "Acceso de usuario con privilegios mínimos", comprobaciones de integridad del código y aislamiento de privilegios.  
  
#### <a name="user-account-control-uac"></a>Control de cuentas de usuario [UAC]  
 Hoy en día, los usuarios de Windows tienden a ejecutarse con privilegios de administrador porque muchas aplicaciones los requieren para la instalación o ejecución, o ambos. Ser capaz de escribir la configuración predeterminada de una aplicación en el Registro es un ejemplo.  
  
 La ejecución con privilegios de administrador en realidad significa que las aplicaciones se ejecutan a partir de procesos que tienen concedidos privilegios de administrador. El efecto de esto en la seguridad es que cualquier código malintencionado que secuestre un proceso que se ejecuta con privilegios de administrador heredará automáticamente esos privilegios, incluido el acceso a recursos críticos del sistema.  
  
 Una manera de protegerse frente a esta amenaza de seguridad es ejecutar las aplicaciones con los privilegios mínimos necesarios. Esto se conoce como el principio de privilegios mínimos y es una característica principal del sistema operativo Windows. Esta característica se denomina Control de cuentas de usuario (UAC) y Windows UAC la utiliza de dos maneras clave:  
  
- Para ejecutar la mayoría de las aplicaciones con privilegios UAC de forma predeterminada, incluso si el usuario es un administrador; solo las aplicaciones que necesitan privilegios de administrador se ejecutarán con privilegios de administrador. Para ejecutarse con privilegios de administrador, las aplicaciones deben marcarse explícitamente en su manifiesto de aplicación o como entrada en la directiva de seguridad.  
  
- Para proporcionar soluciones de compatibilidad como la virtualización. Por ejemplo, muchas aplicaciones intentan escribir en ubicaciones restringidas, como C:\Archivos de programa. Para las aplicaciones que se ejecutan con UAC, existe una ubicación por usuario alternativa que no requiere privilegios de administrador para escribir en ella. Para las aplicaciones que se ejecutan en UAC, UAC virtualiza C:\Archivos de programa para que las aplicaciones que crean estar escribiendo en esa ubicación, en realidad lo estén haciendo en la ubicación por usuario alternativa. Este tipo de trabajo de compatibilidad permite al sistema operativo ejecutar muchas aplicaciones que anteriormente no se podían ejecutar en UAC.  
  
#### <a name="code-integrity-checks"></a>Comprobaciones de integridad de código  
 Windows Vista incorpora comprobaciones de integridad de código más profundas para ayudar a evitar que se inyecte código malintencionado en los archivos del sistema o en el kernel en tiempo de carga/ejecución. Esto va más allá de la protección de archivos de sistema.  

### <a name="limited-rights-process-for-browser-hosted-applications"></a>Proceso de derechos limitados para las aplicaciones hospedadas en explorador  
 Las aplicaciones WPF hospedadas en el explorador se ejecutan en el entorno limitado de la zona de Internet. La integración de WPF con Microsoft Internet Explorer amplía esta protección con compatibilidad adicional.  
  
 Dado que las aplicaciones de explorador XAML (XBAP) suelen estar en espacio aislado por el conjunto de permisos de zona de Internet, quitar estos privilegios no daña las aplicaciones de explorador XAML (XBAP) desde una perspectiva de compatibilidad. En su lugar, se crea una capa adicional de defensa en profundidad; aunque una aplicación en espacio aislado sea capaz de vulnerar otras capas y secuestrar el proceso, el proceso solo tendrá privilegios limitados.  
  
 Consulte [Uso de una cuenta de usuario con privilegios mínimos](https://docs.microsoft.com/previous-versions/tn-archive/cc700846%28v=technet.10%29).  
  
## <a name="common-language-runtime-security"></a>Seguridad de Common Language Runtime  
 Common Language Runtime (CLR) ofrece una serie de ventajas de seguridad clave que incluyen validación y verificación, seguridad de acceso de código (CAS) y la metodología crítica de seguridad.  

### <a name="validation-and-verification"></a>Validación y comprobación  
 Para proporcionar aislamiento e integridad del ensamblado, CLR usa un proceso de validación. La validación de CLR garantiza que los ensamblados se aíslen validando su formato de archivo ejecutable portátil (PE) para las direcciones que apuntan fuera del ensamblado. La validación de CLR también valida la integridad de los metadatos incrustados en un ensamblado.  
  
 Para garantizar la seguridad de tipos, ayudar a evitar problemas de seguridad comunes (por ejemplo, saturaciones de búfer) y habilitar el espacio aislado a través del aislamiento de subprocesos, la seguridad clr usa el concepto de verificación.  
  
 Las aplicaciones administradas se compilan en Lenguaje Intermedio de Microsoft (MSIL). Cuando se ejecutan métodos en una aplicación administrada, su MSIL se compila en código nativo a través de la compilación Just-In-Time (JIT). La compilación JIT incluye un proceso de comprobación que aplica numerosas reglas de seguridad y solidez para impedir que el código realice las siguientes acciones:  
  
- Infringir contratos de tipo  
  
- Introducir saturaciones del búfer  
  
- Tener acceso descontrolado a la memoria  
  
 El código administrado que no cumple las reglas de comprobación no tiene permiso para ejecutarse, a menos que se considere código de confianza.  
  
 La ventaja del código comprobable es una razón clave por la que WPFWPF se basa en .NET Framework. En la medida en que se usa el código comprobable, se reduce en gran medida la posibilidad de aprovecharse de las posibles vulnerabilidades.  
  
### <a name="code-access-security"></a>Seguridad de acceso del código  
 Una máquina cliente exhibe una amplia variedad de recursos a los que puede tener acceso una aplicación administrada, incluido el sistema de archivos, el Registro, los servicios de impresión, la interfaz de usuario, la reflexión y las variables de entorno. Para que una aplicación administrada pueda tener acceso a cualquiera de los recursos de un equipo cliente, debe tener permiso de .NET Framework para hacerlo. Un permiso en CAS es <xref:System.Security.CodeAccessPermission>una subclase de la ; CAS implementa una subclase para cada recurso al que pueden tener acceso las aplicaciones administradas.  
  
 El conjunto de permisos que CAS concede a una aplicación administrada cuando comienza a ejecutarse se conoce como conjunto de permisos y está determinado por la evidencia proporcionada por la aplicación. Para las aplicaciones WPFWPF, la evidencia que se proporciona es la ubicación o zona desde la que se inician las aplicaciones. CAS identifica las siguientes zonas:  
  
- **Mi PC**. Aplicaciones iniciadas desde la máquina cliente (de plena confianza).  
  
- **Intranet local**. Aplicaciones iniciadas desde la intranet (de confianza parcial).  
  
- **Internet**. Aplicaciones iniciadas desde Internet (de confianza mínima).  
  
- **Sitios de confianza**. Aplicaciones identificadas por un usuario como de confianza (de confianza mínima).  
  
- **Sitios que no son de confianza**. Aplicaciones identificadas por un usuario como no confiables (no confiables).  
  
 Para cada una de estas zonas, CAS proporciona un conjunto de permisos predefinido que incluye los permisos que coinciden con el nivel de confianza asociado a cada una. Entre ellas se incluyen las siguientes:  
  
- **FullTrust**. Para aplicaciones iniciadas desde la zona **Mi PC.** Se conceden todos los permisos posibles.  
  
- **LocalIntranet**. Para aplicaciones lanzadas desde la zona **Intranet local.** Un subconjunto de los permisos se concede para proporcionar acceso moderado a los recursos de una máquina cliente, incluido almacenamiento aislado, acceso sin restricciones a la interfaz de usuario, cuadros de diálogo de archivos sin restricciones, reflexión limitada y acceso limitado a las variables de entorno. No se proporcionan permisos para los recursos críticos, como el Registro.  
  
- **Internet**. Para aplicaciones lanzadas desde **Internet** o la zona Sitios **de confianza.** Un subconjunto de los permisos se concede para proporcionar acceso limitado a los recursos de una máquina cliente, incluido almacenamiento aislado, apertura exclusiva de archivos e interfaz de usuario limitada. Esencialmente, este conjunto de permisos aísla las aplicaciones del equipo cliente.  
  
 LAS aplicaciones identificadas como de la zona **Sitios** no confiables no reciben ningún permiso por parte de CAS. Por lo tanto, no existe un conjunto de permisos predefinidos para ellas.  
  
 La siguiente ilustración ilustra la relación entre zonas, conjuntos de permisos, permisos y recursos:  
  
 ![Diagrama que muestra los conjuntos de permisos CAS.](./media/wpf-security-strategy-platform-security/code-access-security-permissions-relationship.png)  
  
 Las restricciones del entorno limitado de seguridad de zona de Internet se aplican por igual a cualquier código que un XBAP importe desde una biblioteca del sistema, incluido WPF. Esto garantiza que cada bit del código está bloqueado, incluso WPFWPF. Desafortunadamente, para poder ejecutar, un XBAP necesita ejecutar una funcionalidad que requiere más permisos que los habilitados por el entorno limitado de seguridad de la zona de Internet.  
  
 Considere una aplicación XBAP que incluya la siguiente página:  
  
 [!code-csharp[WPFPlatformSecuritySnippets#Permission](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/CSharp/Page1.xaml.cs#permission)]
 [!code-vb[WPFPlatformSecuritySnippets#Permission](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/VisualBasic/Page1.xaml.vb#permission)]  
  
 Para ejecutar este XBAP, el código WPF subyacente debe ejecutar más funcionalidad de la que está disponible para el XBAP que realiza la llamada, lo que incluye:  
  
- Creación de un identificador de ventana (HWND) para renderizar  
  
- Envío de mensajes  
  
- Carga de la fuente Tahoma  
  
 Desde el un punto de vista de la seguridad, permitir el acceso directo a cualquiera de estas operaciones desde la aplicación en espacio aislado resultaría catastrófico.  
  
 Afortunadamente, WPFWPF satisface esta situación al permitir que estas operaciones se ejecuten con privilegios elevados en nombre de la aplicación de espacio aislado. Mientras que todas las operaciones de WPFWPF se comprueban con los permisos de seguridad de zona de Internet limitada del dominio de aplicación de La XBAP, WPF (como con otras bibliotecas del sistema) se concede un conjunto de permisos que incluye todos los permisos posibles.
  
 Esto requiere que WPFWPF reciba privilegios elevados mientras impide que esos privilegios se rijan por el conjunto de permisos de zona de Internet del dominio de aplicación host.  
  
 WPFWPF hace esto mediante el uso de la **Assert** método de un permiso. El siguiente código muestra cómo se produce esto:  
  
 [!code-csharp[WPFPlatformSecuritySnippets#Permission](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/CSharp/Page1.xaml.cs#permission)]
 [!code-vb[WPFPlatformSecuritySnippets#Permission](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/VisualBasic/Page1.xaml.vb#permission)]  
  
 **El Assert** esencialmente impide que los permisos ilimitados requeridos por WPFWPF se restrinja por los permisos de zona de Internet de la XBAP.  
  
 Desde una perspectiva de plataforma, WPFWPF es responsable de usar **Assert** correctamente; un uso incorrecto de **Assert** podría permitir que el código malintencionado eleve los privilegios. Por lo tanto, es importante llamar solo a **Assert** cuando sea necesario y asegurarse de que las restricciones de espacio aislado permanecen intactas. Por ejemplo, el código en espacio aislado no tiene permiso para abrir archivos aleatorios, pero sí para usar fuentes. WPFWPF permite que las aplicaciones de espacio aislado usen la funcionalidad de fuente mediante una llamada a **Assert**y para WPFWPF para leer archivos que se sabe que contienen esas fuentes en nombre de la aplicación de espacio aislado.  
  
### <a name="clickonce-deployment"></a>Implementación ClickOnce  
 ClickOnce es una tecnología de implementación completa que se incluye con .NET Framework y se integra con Visual Studio (consulte [Seguridad e implementación](/visualstudio/deployment/clickonce-security-and-deployment) de ClickOnce para obtener información detallada). Las aplicaciones WPF independientes se pueden implementar mediante ClickOnce, mientras que las aplicaciones hospedadas en el explorador deben implementarse con ClickOnce.  
  
 Las aplicaciones implementadas con ClickOnce reciben una capa de seguridad adicional sobre Code Access Security (CAS); esencialmente, ClickOnce ClickOnce aplicación de aplicaciones implementadas solicitar los permisos que necesitan. Esos permisos se les conceden únicamente si no exceden el conjunto de permisos para la zona desde la que se implementa la aplicación. Al reducir el conjunto de permisos solo a los que se necesitan, incluso si son menores que los proporcionados por el conjunto de permisos de la zona de lanzamiento, el número de recursos a los que la aplicación tiene acceso se reduce al mínimo. Por lo tanto, si se secuestra la aplicación, se reduce la posibilidad de daños en la máquina cliente.  
  
### <a name="security-critical-methodology"></a>Metodología crítica para la seguridad  
 El código WPFWPF que usa permisos para habilitar el entorno limitado de zona de Internet para aplicaciones XBAP debe mantenerse con el mayor grado posible de auditoría y control de seguridad. Para facilitar este requisito, .NET Framework proporciona nueva compatibilidad para administrar código que eleva los privilegios. En concreto, CLR permite identificar código que eleva los <xref:System.Security.SecurityCriticalAttribute>privilegios y marcarlo con el ; cualquier código no <xref:System.Security.SecurityCriticalAttribute> marcado se vuelve *transparente* utilizando esta metodología. Por el contrario, se impide que el código administrado que no está marcado con <xref:System.Security.SecurityCriticalAttribute> eleve sus privilegios.  
  
 La metodología crítica para la seguridad permite la organización de código WPFWPF que eleva los privilegios en kernel crítico para la *seguridad,* siendo el resto transparente. Aislar el código crítico para la seguridad permite al equipo de ingeniería de WPF centrar un análisis de seguridad adicional y un control de código fuente en el kernel crítico para la seguridad más allá de las prácticas de seguridad estándar (consulte Estrategia de seguridad de [WPF - Ingeniería](wpf-security-strategy-security-engineering.md)de seguridad ).  
  
 Tenga en cuenta que .NET Framework permite que el código de confianza extienda el <xref:System.Security.AllowPartiallyTrustedCallersAttribute> entorno limitado de la zona de Internet XBAP al permitir a los desarrolladores escribir ensamblados administrados marcados con (APTCA) e implementados en la caché global de ensamblados (GAC) del usuario. Marcar un ensamblado con APTCA es una operación de seguridad muy sensible ya que permite que cualquier código llame a ese ensamblado, incluso el código malintencionado procedente de Internet. Cuando lo haga, extreme las precauciones y siga los procedimientos recomendados; asimismo, los usuarios deben confiar en el software para que pueda instalarse.  
  
## <a name="microsoft-internet-explorer-security"></a>Seguridad de Microsoft Internet Explorer  
 Además de reducir los problemas de seguridad y simplificar la configuración de seguridad, Microsoft Internet Explorer 6 (SP2) contiene varias características que mejoran la seguridad para los usuarios de aplicaciones de explorador XAML (XBAP). Estas características intentan ofrecer a los usuarios un mayor control sobre su experiencia de exploración.  
  
 Antes de IE6 SP2, los usuarios podían estar sujetos a cualquiera de las siguientes opciones:  
  
- Ventanas emergentes aleatorias.  
  
- Redirección de script confusa.  
  
- Numerosos cuadros de diálogo de seguridad en algunos sitios web.  
  
 En algunos casos, los sitios Web no confiables intentarían [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] engañar a los usuarios suplantando la instalación o mostrando repetidamente un cuadro de diálogo de instalación activeX de Microsoft, aunque el usuario lo haya cancelado. Es posible que estas técnicas indujeran a un número significativo de usuarios a tomar malas decisiones que hayan dado lugar a la instalación de aplicaciones de spyware.  
  
 IE6 SP2 incluye varias características para mitigar estos tipos de problemas, que giran en torno al concepto de iniciación del usuario. IE6 SP2 detecta cuando un usuario ha hecho clic en un vínculo o elemento de página antes de una acción, que se conoce como iniciación de *usuario,* y lo trata de forma diferente que cuando el script de una página desencadena una acción similar. Por ejemplo, IE6 SP2 incorpora un **bloqueador de** elementos emergentes que detecta cuando un usuario hace clic en un botón antes de que la página cree una ventana emergente. Esto permite Que IE6 SP2 permita la mayoría de las ventanas emergentes inocuas mientras se evitan las ventanas emergentes que los usuarios ni piden ni quieren. Las ventanas emergentes bloqueadas están atrapadas bajo la nueva barra de **información,** que permite al usuario anular manualmente el bloque y ver la ventana emergente.  
  
 La misma lógica de inicio de usuario también se aplica a las solicitudes de seguridad **Abrir**/**guardar.** Los cuadros de diálogo de instalación ActiveX siempre están atrapados en la barra de información a menos que representen una actualización de un control instalado anteriormente. Estas medidas se combinan para brindar a los usuarios una experiencia de usuario más segura y controlada, puesto que están protegidos contra los sitios que les importunan para instalar software malintencionado o no deseado.  
  
 Estas características también protegen a los clientes que usan IE6 SP2 para navegar a sitios web que les permiten descargar e instalar aplicaciones WPF. En particular, esto se debe a que IE6 SP2 ofrece una mejor experiencia de usuario que reduce la posibilidad de que los usuarios instalen aplicaciones malintencionadas o torpes independientemente de la tecnología que se haya utilizado para compilarla, incluido WPF. WPFWPF se agrega a estas protecciones mediante ClickOnce para facilitar la descarga de sus aplicaciones a través de Internet. Dado que las aplicaciones de explorador XAML (XBAP) se ejecutan dentro de un entorno limitado de seguridad de zona de Internet, se pueden iniciar sin problemas. Por otro lado, las aplicaciones WPF independientes requieren plena confianza para ejecutarse. Para estas aplicaciones, ClickOnce ClickOnce mostrará un cuadro de diálogo de seguridad durante el proceso de inicio para notificar el uso de los requisitos de seguridad adicionales de la aplicación. Sin embargo, esto debe ser iniciado por el usuario, se regirá por la lógica iniciada por el usuario y se puede cancelar.  
  
 Internet Explorer 7 incorpora y amplía las capacidades de seguridad de IE6 SP2 como parte de un compromiso continuo con la seguridad.  
  
## <a name="see-also"></a>Consulte también

- [Seguridad de acceso al código](../misc/code-access-security.md)
- [Seguridad](security-wpf.md)
- [Seguridad de confianza parcial de WPF](wpf-partial-trust-security.md)
- [Estrategia de seguridad de WPF: Ingeniería de seguridad](wpf-security-strategy-security-engineering.md)
