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
ms.openlocfilehash: 4fa01922c5c3097adb124d67272b9f449b70ada3
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "76979877"
---
# <a name="wpf-security-strategy---platform-security"></a>Estrategia de seguridad de WPF: Seguridad de plataforma
Aunque Windows Presentation Foundation (WPF) proporciona una gran variedad de servicios de seguridad, también aprovecha las características de seguridad de la plataforma subyacente, que incluye el sistema operativo, CLR e Internet Explorer. Estas capas se combinan para proporcionar a WPF un modelo de seguridad sólido y de defensa en profundidad que intenta evitar cualquier punto único de error, como se muestra en la ilustración siguiente:  
  
 ![Diagrama que muestra el modelo de seguridad de WPF.](./media/wpf-security-strategy-platform-security/windows-presentation-foundation-security.png)  
  
 En el resto de este tema se describen las características de cada una de estas capas que pertenecen específicamente a WPF.  

## <a name="operating-system-security"></a>Seguridad del sistema operativo  
El núcleo de Windows proporciona varias características de seguridad que forman la base de seguridad para todas las aplicaciones de Windows, incluidas las creadas con WPF. En este tema se describe el alcance de estas características de seguridad que son importantes para WPF, así como la forma en que WPF se integra con ellas para proporcionar una mayor defensa en profundidad.  
  
### <a name="microsoft-windows-xp-service-pack-2-sp2"></a>Microsoft Windows XP Service Pack 2 (SP2)  
 Además de una revisión general y el fortalecimiento de Windows, hay tres características clave de Windows XP SP2 que se tratarán en este tema:  
  
- Compilación /GS  
  
- Microsoft Windows Update.  
  
#### <a name="gs-compilation"></a>Compilación /GS  
 Windows XP SP2 proporciona protección al volver a compilar muchas bibliotecas de sistema principales, incluidas todas las dependencias de WPF, como CLR, para ayudar a mitigar las saturaciones del búfer. Esto se logra usando el parámetro /GS con el compilador de línea de comandos de C o C++. Aunque las saturaciones del búfer se deben evitar de manera explícita, la compilación /GS proporciona un ejemplo de una defensa en profundidad contra posibles vulnerabilidades creadas por dichas saturaciones de forma accidental o malintencionada.  
  
 Históricamente, las saturaciones del búfer han sido la causa de muchas vulnerabilidades de seguridad de gran impacto. Una saturación del búfer se produce cuando un atacante aprovecha una vulnerabilidad de código que permite la inserción de código malintencionado que escribe más allá de los límites de un búfer. Esto permite a un atacante secuestrar el proceso en el que se ejecuta el código; para ello, se sobrescribe la dirección de retorno de una función para que se ejecute el código del atacante. El resultado es un código malintencionado que ejecuta código arbitrario con los mismos privilegios que el proceso atacado.  
  
 En un nivel alto, la marca del compilador-GS protege frente a algunas saturaciones de búfer potenciales mediante la inserción de una cookie de seguridad especial que protege la dirección de retorno de una función que tiene búferes de cadena locales. Una vez que se devuelve una función, la cookie de seguridad se compara con su valor anterior. Si el valor cambia, puede deberse a una saturación del búfer y el proceso se detiene con una condición de error. Detener el proceso impide la ejecución de código potencialmente malintencionado. Consulte [-GS (comprobación de seguridad del búfer)](/cpp/build/reference/gs-buffer-security-check) para obtener más detalles.  
  
 WPF se compila con la marca/GS para agregar aún otro nivel de defensa a las aplicaciones de WPF.  
  
### <a name="windows-vista"></a>Windows Vista  
Los usuarios de WPF en Windows Vista se beneficiarán de las mejoras de seguridad adicionales del sistema operativo, como "acceso de usuario con privilegios mínimos", comprobaciones de integridad de código y aislamiento de privilegios.  
  
#### <a name="user-account-control-uac"></a>Control de cuentas de usuario [UAC]  
 Hoy en día, los usuarios de Windows tienden a ejecutarse con privilegios de administrador porque muchas aplicaciones los requieren para la instalación o la ejecución, o para ambos. Ser capaz de escribir la configuración predeterminada de una aplicación en el Registro es un ejemplo.  
  
 La ejecución con privilegios de administrador en realidad significa que las aplicaciones se ejecutan a partir de procesos que tienen concedidos privilegios de administrador. El efecto de esto en la seguridad es que cualquier código malintencionado que secuestre un proceso que se ejecuta con privilegios de administrador heredará automáticamente esos privilegios, incluido el acceso a recursos críticos del sistema.  
  
 Una manera de protegerse frente a esta amenaza de seguridad es ejecutar las aplicaciones con los privilegios mínimos necesarios. Esto se conoce como el principio de privilegios mínimos y es una característica fundamental del sistema operativo Windows. Esta característica se denomina control de cuentas de usuario (UAC) y Windows UAC la usa de dos maneras principales:  
  
- Para ejecutar la mayoría de las aplicaciones con privilegios UAC de forma predeterminada, incluso si el usuario es un administrador; solo las aplicaciones que necesitan privilegios de administrador se ejecutarán con privilegios de administrador. Para ejecutarse con privilegios de administrador, las aplicaciones deben marcarse explícitamente en su manifiesto de aplicación o como entrada en la directiva de seguridad.  
  
- Para proporcionar soluciones de compatibilidad como la virtualización. Por ejemplo, muchas aplicaciones intentan escribir en ubicaciones restringidas, como C:\Archivos de programa. Para las aplicaciones que se ejecutan con UAC, existe una ubicación por usuario alternativa que no requiere privilegios de administrador para escribir en ella. Para las aplicaciones que se ejecutan en UAC, UAC virtualiza C:\Archivos de programa para que las aplicaciones que crean estar escribiendo en esa ubicación, en realidad lo estén haciendo en la ubicación por usuario alternativa. Este tipo de trabajo de compatibilidad permite al sistema operativo ejecutar muchas aplicaciones que anteriormente no se podían ejecutar en UAC.  
  
#### <a name="code-integrity-checks"></a>Comprobaciones de integridad de código  
 Windows Vista incorpora comprobaciones de integridad de código más profundas para ayudar a evitar que se inserte código malintencionado en los archivos del sistema o en el kernel en tiempo de carga o de ejecución. Esto va más allá de la protección de archivos de sistema.  
   
### <a name="limited-rights-process-for-browser-hosted-applications"></a>Proceso de derechos limitados para las aplicaciones hospedadas en explorador  
 Las aplicaciones WPF hospedadas en explorador se ejecutan en el espacio aislado de zona de Internet. La integración de WPF con Microsoft Internet Explorer amplía esta protección con compatibilidad adicional.  
  
 Dado que las aplicaciones de explorador XAML (XBAP) suelen estar en un espacio aislado por el conjunto de permisos de la zona de Internet, la eliminación de estos privilegios no daña las aplicaciones de explorador XAML (XBAP) desde una perspectiva de compatibilidad. En su lugar, se crea una capa adicional de defensa en profundidad; aunque una aplicación en espacio aislado sea capaz de vulnerar otras capas y secuestrar el proceso, el proceso solo tendrá privilegios limitados.  
  
 Consulte [uso de una cuenta de usuario con privilegios mínimos](https://docs.microsoft.com/previous-versions/tn-archive/cc700846%28v=technet.10%29).  
  
## <a name="common-language-runtime-security"></a>Seguridad de Common Language Runtime  
 El Common Language Runtime (CLR) ofrece una serie de ventajas clave de seguridad que incluyen validación y comprobación, seguridad de acceso del código (CAS) y la metodología crítica para la seguridad.  
    
### <a name="validation-and-verification"></a>Validación y comprobación  
 Para proporcionar aislamiento de ensamblado e integridad, CLR usa un proceso de validación. La validación de CLR garantiza que los ensamblados están aislados mediante la validación de su formato de archivo portable ejecutable (PE) para las direcciones que apuntan fuera del ensamblado. La validación de CLR también valida la integridad de los metadatos que se incrustan dentro de un ensamblado.  
  
 Para garantizar la seguridad de tipos, evitar problemas de seguridad comunes (por ejemplo, saturaciones del búfer) y habilitar el espacio aislado mediante el aislamiento de subprocesos, la seguridad de CLR utiliza el concepto de comprobación.  
  
 Las aplicaciones administradas se compilan en Lenguaje Intermedio de Microsoft (MSIL). Cuando se ejecutan métodos en una aplicación administrada, su MSIL se compila en código nativo a través de la compilación Just-In-Time (JIT). La compilación JIT incluye un proceso de comprobación que aplica numerosas reglas de seguridad y solidez para impedir que el código realice las siguientes acciones:  
  
- Infringir contratos de tipo  
  
- Introducir saturaciones del búfer  
  
- Tener acceso descontrolado a la memoria  
  
 El código administrado que no cumple las reglas de comprobación no tiene permiso para ejecutarse, a menos que se considere código de confianza.  
  
 La ventaja del código comprobable es una razón clave por la que WPF se basa en el .NET Framework. En la medida en que se usa el código comprobable, se reduce en gran medida la posibilidad de aprovecharse de las posibles vulnerabilidades.  
  
### <a name="code-access-security"></a>Seguridad de acceso del código  
 Una máquina cliente exhibe una amplia variedad de recursos a los que puede tener acceso una aplicación administrada, incluido el sistema de archivos, el Registro, los servicios de impresión, la interfaz de usuario, la reflexión y las variables de entorno. Para que una aplicación administrada pueda tener acceso a cualquiera de los recursos de un equipo cliente, debe tener .NET Framework permiso para hacerlo. Un permiso en CAS es una subclase del <xref:System.Security.CodeAccessPermission>; CAS implementa una subclase para cada recurso al que pueden tener acceso las aplicaciones administradas.  
  
 El conjunto de permisos que las entidades de certificación conceden a una aplicación administrada cuando comienza a ejecutarse se conoce como conjunto de permisos y viene determinado por la evidencia proporcionada por la aplicación. En el caso de las aplicaciones de WPF, la evidencia proporcionada es la ubicación, o zona, desde la que se inician las aplicaciones. CA identifica las zonas siguientes:  
  
- **Mi PC**. Aplicaciones iniciadas desde la máquina cliente (de plena confianza).  
  
- **Intranet local**. Aplicaciones iniciadas desde la intranet (de confianza parcial).  
  
- **Internet**. Aplicaciones iniciadas desde Internet (de confianza mínima).  
  
- **Sitios de confianza**. Aplicaciones identificadas por un usuario como de confianza (de confianza mínima).  
  
- **Sitios que no son de confianza**. Aplicaciones identificadas por un usuario como no confiables (no confiables).  
  
 Para cada una de estas zonas, CAS proporciona un conjunto de permisos predefinidos que incluye los permisos que coinciden con el nivel de confianza asociado a cada uno de ellos. Se incluyen los siguientes:  
  
- **FullTrust**. Para las aplicaciones iniciadas desde la zona **mi PC** . Se conceden todos los permisos posibles.  
  
- **LocalIntranet**. Para las aplicaciones iniciadas desde la zona de **Intranet local** . Un subconjunto de los permisos se concede para proporcionar acceso moderado a los recursos de una máquina cliente, incluido almacenamiento aislado, acceso sin restricciones a la interfaz de usuario, cuadros de diálogo de archivos sin restricciones, reflexión limitada y acceso limitado a las variables de entorno. No se proporcionan permisos para los recursos críticos, como el Registro.  
  
- **Internet**. Para las aplicaciones iniciadas desde la zona **Internet** o **sitios de confianza** . Un subconjunto de los permisos se concede para proporcionar acceso limitado a los recursos de una máquina cliente, incluido almacenamiento aislado, apertura exclusiva de archivos e interfaz de usuario limitada. En esencia, este conjunto de permisos aísla las aplicaciones del equipo cliente.  
  
 Las aplicaciones identificadas como procedentes de la zona de sitios que no son de **confianza** no tienen permisos para las entidades de certificación. Por lo tanto, no existe un conjunto de permisos predefinidos para ellas.  
  
 En la ilustración siguiente se muestra la relación entre zonas, conjuntos de permisos, permisos y recursos:  
  
 ![Diagrama que muestra los conjuntos de permisos de CAS.](./media/wpf-security-strategy-platform-security/code-access-security-permissions-relationship.png)  
  
 Las restricciones del espacio aislado de seguridad de la zona de Internet se aplican igualmente a cualquier código que una aplicación XBAP importe desde una biblioteca del sistema, incluido WPF. Esto garantiza que cada bit del código está bloqueado, incluso WPF. Desafortunadamente, para poder ejecutar, una aplicación XBAP necesita ejecutar funcionalidad que requiere más permisos que los habilitados por el espacio aislado de seguridad de la zona de Internet.  
  
 Considere una aplicación XBAP que incluye la siguiente página:  
  
 [!code-csharp[WPFPlatformSecuritySnippets#Permission](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/CSharp/Page1.xaml.cs#permission)]
 [!code-vb[WPFPlatformSecuritySnippets#Permission](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/VisualBasic/Page1.xaml.vb#permission)]  
  
 Para ejecutar esta aplicación XBAP, el código subyacente de WPF debe ejecutar más funcionalidad de la que está disponible para la aplicación XBAP que realiza la llamada, entre las que se incluyen:  
  
- Crear un identificador de ventana (HWND) para la representación  
  
- Envío de mensajes  
  
- Carga de la fuente Tahoma  
  
 Desde el un punto de vista de la seguridad, permitir el acceso directo a cualquiera de estas operaciones desde la aplicación en espacio aislado resultaría catastrófico.  
  
 Afortunadamente, WPF se encarga de esta situación, ya que permite que estas operaciones se ejecuten con privilegios elevados en nombre de la aplicación en espacio aislado. Aunque todas las operaciones de WPF se comprueban con los permisos limitados de seguridad de la zona de Internet del dominio de aplicación de la aplicación XBAP, WPF (al igual que con otras bibliotecas del sistema) se le concede un conjunto de permisos que incluye todos los permisos posibles.
  
 Esto requiere que WPF reciba privilegios elevados, a la vez que evita que esos privilegios se rijan por el conjunto de permisos de la zona de Internet del dominio de la aplicación host.  
  
 Para ello, WPF usa el método **Assert** de un permiso. El siguiente código muestra cómo se produce esto:  
  
 [!code-csharp[WPFPlatformSecuritySnippets#Permission](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/CSharp/Page1.xaml.cs#permission)]
 [!code-vb[WPFPlatformSecuritySnippets#Permission](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFPlatformSecuritySnippets/VisualBasic/Page1.xaml.vb#permission)]  
  
 Esencialmente, la **aserción** evita que los permisos ilimitados requeridos por WPF estén restringidos por los permisos de la zona de Internet de la aplicación XBAP.  
  
 Desde la perspectiva de la plataforma, WPF es responsable de usar **Assert** correctamente; un uso incorrecto de **Assert** podría permitir que el código malintencionado eleve los privilegios. Por lo tanto, es importante llamar a **Assert** únicamente cuando sea necesario y asegurarse de que las restricciones de espacio aislado permanecen intactas. Por ejemplo, el código en espacio aislado no tiene permiso para abrir archivos aleatorios, pero sí para usar fuentes. WPF permite que las aplicaciones en espacio aislado usen la funcionalidad de fuentes mediante una llamada a **Assert**y que WPF Lea los archivos que se sabe que contienen esas fuentes en nombre de la aplicación en espacio aislado.  
  
### <a name="clickonce-deployment"></a>Implementación ClickOnce  
 ClickOnce es una tecnología de implementación completa que se incluye con .NET Framework y se integra con Visual Studio (consulte [seguridad e implementación de ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment) para obtener información detallada). Las aplicaciones de WPF independientes se pueden implementar mediante ClickOnce, mientras que las aplicaciones hospedadas en explorador deben implementarse con ClickOnce.  
  
 Las aplicaciones implementadas mediante ClickOnce reciben un nivel de seguridad adicional sobre la seguridad de acceso del código (CAS). esencialmente, las aplicaciones implementadas por ClickOnce solicitan los permisos que necesitan. Esos permisos se les conceden únicamente si no exceden el conjunto de permisos para la zona desde la que se implementa la aplicación. Al reducir el conjunto de permisos a solo los necesarios, incluso si son menores que los proporcionados por el conjunto de permisos de la zona de inicio, el número de recursos a los que tiene acceso la aplicación se reduce al mínimo. Por lo tanto, si se secuestra la aplicación, se reduce la posibilidad de daños en la máquina cliente.  
  
### <a name="security-critical-methodology"></a>Metodología crítica para la seguridad  
 El código de WPF que usa permisos para habilitar el espacio aislado de zona de Internet para aplicaciones XBAP debe mantenerse en el mayor grado posible de auditoría y control de seguridad. Para facilitar este requisito, .NET Framework proporciona nueva compatibilidad para administrar el código que eleva los privilegios. En concreto, CLR permite identificar el código que eleva los privilegios y lo marca con el <xref:System.Security.SecurityCriticalAttribute>; cualquier código no marcado con <xref:System.Security.SecurityCriticalAttribute> se vuelve *transparente* mediante esta metodología. Por el contrario, se impide que el código administrado que no está marcado con <xref:System.Security.SecurityCriticalAttribute> eleve sus privilegios.  
  
 La metodología crítica para la seguridad permite a la organización de código de WPF que eleva los privilegios en el *kernel crítico para la seguridad*, con lo que el resto es transparente. Aislar el código crítico para la seguridad permite al equipo de ingeniería de WPF centrarse en un análisis de seguridad y control de código fuente adicional en el kernel crítico para la seguridad más allá de las prácticas de seguridad estándar (consulte [estrategia de seguridad de WPF: Ingeniería de seguridad](wpf-security-strategy-security-engineering.md)).  
  
 Tenga en cuenta que .NET Framework permite que el código de confianza amplíe el espacio aislado de la zona de Internet de XBAP permitiendo a los desarrolladores escribir ensamblados administrados marcados con <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) e implementados en la caché de ensamblados global (GAC) del usuario. Marcar un ensamblado con APTCA es una operación de seguridad muy sensible ya que permite que cualquier código llame a ese ensamblado, incluso el código malintencionado procedente de Internet. Cuando lo haga, extreme las precauciones y siga los procedimientos recomendados; asimismo, los usuarios deben confiar en el software para que pueda instalarse.  
  
## <a name="microsoft-internet-explorer-security"></a>Seguridad de Microsoft Internet Explorer  
 Además de reducir los problemas de seguridad y simplificar la configuración de seguridad, Microsoft Internet Explorer 6 (SP2) contiene varias características que mejoran la seguridad para los usuarios de las aplicaciones de explorador XAML (XBAP). Estas características intentan ofrecer a los usuarios un mayor control sobre su experiencia de exploración.  
  
 Antes de IE6 SP2, los usuarios podían estar sujetos a lo siguiente:  
  
- Ventanas emergentes aleatorias.  
  
- Redirección de script confusa.  
  
- Numerosos cuadros de diálogo de seguridad en algunos sitios web.  
  
 En algunos casos, los sitios web que no son de confianza intentan engañar a los usuarios suplantando la instalación [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] o mostrando repetidamente un cuadro de diálogo de instalación de Microsoft ActiveX, aunque el usuario haya cancelado. Es posible que estas técnicas indujeran a un número significativo de usuarios a tomar malas decisiones que hayan dado lugar a la instalación de aplicaciones de spyware.  
  
 IE6 SP2 incluye varias características para mitigar estos tipos de problemas, que giran en torno al concepto de inicio del usuario. IE6 SP2 detecta cuándo un usuario hizo clic en un vínculo o elemento de página antes de una acción, lo que se conoce como *Inicio de usuario*, y lo trata de forma diferente a cuando una acción similar se desencadena por el script en una página. Por ejemplo, IE6 SP2 incorpora un **bloqueador de elementos emergentes** que detecta si un usuario hace clic en un botón antes de que la página cree un elemento emergente. Esto permite a IE6 SP2 permitir la mayoría de los elementos emergentes inocuos a la vez que se evitan los elementos emergentes que los usuarios no solicitan ni desean. Los elementos emergentes bloqueados se capturan en la nueva **barra de información**, lo que permite al usuario invalidar manualmente el bloque y ver el elemento emergente.  
  
 También se aplica la misma lógica de inicio de usuario para **abrir**/**Guardar** los mensajes de seguridad. Los cuadros de diálogo de instalación de ActiveX siempre se capturan en la barra de información, a menos que representen una actualización de un control instalado previamente. Estas medidas se combinan para brindar a los usuarios una experiencia de usuario más segura y controlada, puesto que están protegidos contra los sitios que les importunan para instalar software malintencionado o no deseado.  
  
 Estas características también protegen a los clientes que usan IE6 SP2 para ir a sitios web que les permiten descargar e instalar aplicaciones de WPF. En concreto, esto se debe a que IE6 SP2 ofrece una mejor experiencia de usuario que reduce la posibilidad de que los usuarios instalen aplicaciones malintencionadas o dañinass independientemente de qué tecnología se usó para compilarlo, incluido WPF. WPF agrega estas protecciones mediante ClickOnce para facilitar la descarga de sus aplicaciones a través de Internet. Dado que las aplicaciones de explorador XAML (XBAP) se ejecutan en un espacio aislado de seguridad de zona de Internet, pueden iniciarse sin problemas. Por otro lado, las aplicaciones de WPF independientes requieren plena confianza para ejecutarse. Para estas aplicaciones, ClickOnce mostrará un cuadro de diálogo de seguridad durante el proceso de inicio para notificar el uso de los requisitos de seguridad adicionales de la aplicación. Sin embargo, esto debe ser iniciado por el usuario, se regirá por la lógica iniciada por el usuario y se puede cancelar.  
  
 Internet Explorer 7 incorpora y amplía las capacidades de seguridad de IE6 SP2 como parte de un compromiso continuo con la seguridad.  
  
## <a name="see-also"></a>Vea también

- [Seguridad de acceso del código](../misc/code-access-security.md)
- [Seguridad](security-wpf.md)
- [Seguridad de confianza parcial de WPF](wpf-partial-trust-security.md)
- [Estrategia de seguridad de WPF: Ingeniería de seguridad](wpf-security-strategy-security-engineering.md)
