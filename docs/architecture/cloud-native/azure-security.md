---
title: Seguridad de Azure para aplicaciones nativas de la nube
description: Arquitectura de aplicaciones nativas de .NET en la nube para Azure Azure Security for Cloud Native Apps
ms.date: 06/30/2019
ms.openlocfilehash: 13b5ad7a883a83014913fa0a6a020610c28c524f
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989147"
---
# <a name="azure-security-for-cloud-native-apps"></a>Seguridad de Azure para aplicaciones nativas de la nube

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Las aplicaciones nativas de la nube pueden ser más fáciles y difíciles de proteger que las aplicaciones tradicionales. En el lado negativo, necesita proteger más aplicaciones más pequeñas y dedicar más energía para construir la infraestructura de seguridad. La naturaleza heterogénea de los lenguajes y estilos de programación en la mayoría de las implementaciones de servicios también significa que debe prestar más atención a los boletines de seguridad de muchos proveedores diferentes.

Por otro lado, los servicios más pequeños, cada uno con su propio almacén de datos, limitan el alcance de un ataque. Si un atacante pone en peligro un sistema, probablemente sea más difícil para el atacante hacer el salto a otro sistema que en una aplicación monolítica. Los límites del proceso son límites fuertes. Además, si se filtra una copia de seguridad de la base de datos, el daño es más limitado, ya que esa base de datos contiene solo un subconjunto de datos y es poco probable que contenga datos personales.

## <a name="threat-modeling"></a>Modelado de amenazas

No importa si las ventajas superan las desventajas de las aplicaciones nativas de la nube, se debe seguir la misma mentalidad de seguridad holística. La seguridad y el pensamiento seguro deben formar parte de cada paso de la historia de desarrollo y operaciones. Al planificar una solicitud, haga preguntas como:

- ¿Cuál sería el impacto de la pérdida de estos datos?
- ¿Cómo podemos limitar el daño de los datos incorrectos que se inyectan en este servicio?
- ¿Quién debe tener acceso a estos datos?
- ¿Existen políticas de auditoría en el proceso de desarrollo y lanzamiento?

Todas estas preguntas son parte de un proceso llamado modelado de [amenazas.](https://docs.microsoft.com/azure/security/azure-security-threat-modeling-tool) Este proceso trata de responder a la pregunta de qué amenazas hay para el sistema, cuán probables son las amenazas y el daño potencial de ellas.

Una vez que se ha establecido la lista de amenazas, debe decidir si vale la pena mitigarlas. A veces una amenaza es tan improbable y costosa de planear que no vale la pena gastar energía en ella. Por ejemplo, algún actor de nivel de estado podría inyectar cambios en el diseño de un proceso que es utilizado por millones de dispositivos. Ahora, en lugar de ejecutar un cierto fragmento de código en [Ring 3](https://en.wikipedia.org/wiki/Protection_ring), ese código se ejecuta en ring 0. Esto permite un exploit que puede omitir el hipervisor y ejecutar el código de ataque en las máquinas de metal desnudo, lo que permite ataques a todas las máquinas virtuales que se ejecutan en ese hardware.

Los procesadores alterados son difíciles de detectar sin un microscopio y el conocimiento avanzado del diseño de silicio de ese procesador. Es poco probable que este escenario suceda y costoso de mitigar, por lo que probablemente ningún modelo de amenaza recomendaría la creación de protección contra vulnerabilidades para él.

Las amenazas más probables, como `Id` los controles de `Id=2` `Id=3` acceso rotos que permiten el incremento de los ataques (que se reemplazan con en la dirección URL) o la inyección DE SQL, son más atractivas para crear protecciones contra. Las mitigaciones de estas amenazas son bastante razonables para crear y prevenir agujeros de seguridad embarazosos que difuminan la reputación de la empresa.

## <a name="principle-of-least-privilege"></a>Principio de privilegio mínimo

Una de las ideas fundacionales en seguridad informática es el Principio de PrivilegioS Mínimos (POLP). En realidad es una idea fundamental en la mayoría de cualquier forma de seguridad, ya sea digital o física. En resumen, el principio es que cualquier usuario o proceso debe tener el menor número de derechos posible para ejecutar su tarea.

Como ejemplo, piense en los cajeros en un banco: acceder a la caja fuerte es una actividad poco común. Por lo tanto, el cajero promedio no puede abrir la caja fuerte ellos mismos. Para obtener acceso, necesitan aumentar su solicitud a través de un gerente de banco, que realiza comprobaciones de seguridad adicionales.

En un sistema informático, un ejemplo fantástico son los derechos de un usuario que se conecta a una base de datos. En muchos casos, hay una sola cuenta de usuario que se usa para compilar la estructura de la base de datos y ejecutar la aplicación. Excepto en casos extremos, la cuenta que ejecuta la aplicación no necesita la capacidad de actualizar la información del esquema. Debe haber varias cuentas que proporcionen diferentes niveles de privilegios. La aplicación solo debe usar el nivel de permiso que concede acceso de lectura y escritura a los datos de las tablas. Este tipo de protección eliminaría los ataques destinados a quitar tablas de base de datos o introducir desencadenadores malintencionados.

Casi todas las partes de la creación de una aplicación nativa de la nube pueden beneficiarse de recordar el principio de privilegios mínimos. Puede encontrarlo en juego al configurar firewalls, grupos de seguridad de red, roles y ámbitos en El control de acceso basado en roles (RBAC).

## <a name="penetration-testing"></a>Pruebas de penetración

A medida que las aplicaciones se vuelven más complicadas, el número de vectores de ataque aumenta a una velocidad alarmante. El modelado de amenazas es defectuoso en que tiende a ser ejecutado por las mismas personas que construyen el sistema. De la misma manera que muchos desarrolladores tienen problemas para imaginar las interacciones de los usuarios y luego crear interfaces de usuario inutilizables, la mayoría de los desarrolladores tienen dificultades para ver cada vector de ataque. También es posible que los desarrolladores que construyen el sistema no estén bien versados en metodologías de ataque y se pierdan algo crucial.

Las pruebas de penetración o "pruebas de lápiz" implican incorporar actores externos para intentar atacar el sistema. Estos atacantes pueden ser una empresa de consultoría externa u otros desarrolladores con un buen conocimiento de seguridad de otra parte del negocio. Se les da carta blanca para intentar subvertir el sistema. Con frecuencia, encontrarán extensos agujeros de seguridad que deben ser parcheados. A veces el vector de ataque será algo totalmente inesperado como explotar un ataque de phishing contra el CEO.

Azure en sí está constantemente entrando en ataques de un [equipo de hackers dentro](https://azure.microsoft.com/resources/videos/red-vs-blue-internal-security-penetration-testing-of-microsoft-azure/)de Microsoft . A lo largo de los años, han sido los primeros en encontrar docenas de vectores de ataque potencialmente catastróficos, cerrándolos antes de que puedan ser explotados externamente. Cuanto más tentador sea un objetivo, más probable será que los actores eternos intenten explotarlo y hay algunos objetivos en el mundo más tentadores que Azure.

## <a name="monitoring"></a>Supervisión

Si un atacante intenta penetrar una aplicación, debe haber alguna advertencia de ella. Con frecuencia, los ataques se pueden detectar examinando los registros de los servicios. Los ataques dejan señales reveladoras que se pueden detectar antes de que tengan éxito. Por ejemplo, un atacante que intenta adivinar una contraseña hará muchas solicitudes a un sistema de inicio de sesión. La supervisión alrededor del sistema de inicio de sesión puede detectar patrones extraños que están fuera de línea con el patrón de acceso típico. Esta supervisión se puede convertir en una alerta que, a su vez, puede alertar a una persona de operaciones para activar algún tipo de contramedida. Un sistema de monitoreo altamente maduro podría incluso tomar medidas basadas en estas desviaciones de forma proactiva agregando reglas para bloquear solicitudes o limitar las respuestas.

## <a name="securing-the-build"></a>Asegurar la construcción

Un lugar donde la seguridad a menudo se pasa por alto es alrededor del proceso de compilación. No solo la compilación debe ejecutar comprobaciones de seguridad, como el análisis de código inseguro o credenciales protegidas, sino que la compilación en sí debe ser segura. Si el servidor de compilación está en peligro, proporciona un vector fantástico para introducir código arbitrario en el producto.

Imagine que un atacante está buscando robar las contraseñas de las personas que inician sesión en una aplicación web. Podrían introducir un paso de compilación que modifique el código desprotegido para reflejar cualquier solicitud de inicio de sesión en otro servidor. La próxima vez que el código pase por la compilación, se actualizará silenciosamente. El análisis de vulnerabilidades de código fuente no detectará esto mientras se ejecuta antes de la compilación. Del mismo modo, nadie lo detectará en una revisión de código porque los pasos de compilación viven en el servidor de compilación. El código explotado irá a la producción donde puede cosechar contraseñas. Probablemente no hay ningún registro de auditoría de los cambios del proceso de compilación, o al menos nadie supervisando la auditoría.

Este es un ejemplo perfecto de un objetivo de valor aparentemente bajo que se puede utilizar para entrar en el sistema. Una vez que un atacante rompe el perímetro del sistema, puede empezar a trabajar en la búsqueda de maneras de elevar sus permisos hasta el punto de que puede causar daño real en cualquier lugar que desee.

## <a name="building-secure-code"></a>Construyendo código seguro

.NET Framework ya es un marco bastante seguro. Evita algunos de los escollos de código no administrado, como salir de los extremos de las matrices. El trabajo se realiza activamente para arreglar los agujeros de seguridad a medida que se descubren. Incluso hay un programa de recompensa de [errores](https://www.microsoft.com/msrc/bounty) que paga a los investigadores para encontrar problemas en el marco y reportarlos en lugar de explotarlos.

Hay muchas maneras de hacer que el código .NET sea más seguro. Seguir instrucciones como las directrices de [codificación segura para .NET](https://docs.microsoft.com/dotnet/standard/security/secure-coding-guidelines) es un paso razonable para asegurarse de que el código está seguro desde cero. El Top 10 de [OWASP](https://owasp.org/www-project-top-ten/) es otra guía invaluable para crear código seguro.

El proceso de compilación es un buen lugar para poner herramientas de análisis para detectar problemas en el código fuente antes de que se conviertan en producción. La mayoría de los proyectos tienen dependencias en algunos otros paquetes. Una herramienta que puede buscar paquetes obsoletos detectará problemas en una compilación nocturna. Incluso al crear imágenes de Docker, es útil comprobar y asegurarse de que la imagen base no tiene vulnerabilidades conocidas. Otra cosa a comprobar es que nadie ha registrado accidentalmente las credenciales.

## <a name="built-in-security"></a>Seguridad integrada

Azure está diseñado para equilibrar la facilidad de uso y la seguridad de la mayoría de los usuarios. Diferentes usuarios van a tener diferentes requisitos de seguridad, por lo que necesitan ajustar su enfoque de la seguridad en la nube. Microsoft publica una gran cantidad de información de seguridad en el [Centro de confianza](https://azure.microsoft.com/support/trust-center/). Este recurso debe ser la primera parada para aquellos profesionales interesados en entender cómo funcionan las tecnologías de mitigación de ataques integradas.

Dentro de Azure Portal, [Azure Advisor](https://azure.microsoft.com/services/advisor/) es un sistema que analiza constantemente un entorno y hace recomendaciones. Algunas de estas recomendaciones están diseñadas para ahorrar dinero a los usuarios, pero otras están diseñadas para identificar configuraciones potencialmente inseguras, como tener un contenedor de almacenamiento abierto al mundo y no protegido por una red virtual.

## <a name="azure-network-infrastructure"></a>Infraestructura de red de Azure

En un entorno de implementación local, una gran cantidad de energía se dedica a configurar redes. La configuración de enrutadores, conmutadores y, tal, es un trabajo complicado. Las redes permiten que ciertos recursos hablen con otros recursos e impidan el acceso en algunos casos. Una regla de red frecuente consiste en restringir el acceso al entorno de producción desde el entorno de desarrollo con la posibilidad de que un fragmento de código medio desarrollado se ejecute mal y elimine una franja de datos.

De fábrica, la mayoría de los recursos de PaaS Azure solo tienen la configuración de red más básica y permisiva. Por ejemplo, cualquier persona en Internet puede acceder a un servicio de aplicaciones. Las nuevas instancias de SQL ServerSQL Server suelen estar restringidas, por lo que las partes externas no pueden tener acceso a ellas, pero se permiten los intervalos de direcciones IP que usa Azure. Por lo tanto, mientras que el servidor SQL está protegido contra amenazas externas, un atacante solo necesita configurar una cabeza de puente de Azure desde donde puede lanzar ataques contra todas las instancias sql en Azure.

Afortunadamente, la mayoría de los recursos de Azure se pueden colocar en una red virtual de Azure que permite un control de acceso más preciso. De forma similar a la forma en que las redes locales establecen redes privadas protegidas desde el mundo en general, las redes virtuales son islas de direcciones IP privadas que se encuentran dentro de la red de Azure.

![Figura 10-1 Una red](./media/virtual-network.png)
virtual en la**figura 10-1**de Azure. Una red virtual en Azure.

Del mismo modo que las redes locales tienen un firewall que rige el acceso a la red, puede establecer un firewall similar en el límite de la red virtual. De forma predeterminada, todos los recursos de una red virtual todavía pueden hablar con Internet. Son solo las conexiones entrantes que requieren algún tipo de excepción de firewall explícita.

Con la red establecida, los recursos internos como las cuentas de almacenamiento se pueden configurar para permitir solo el acceso de los recursos que también están en la red virtual. Este firewall proporciona un nivel adicional de seguridad, en caso de que se filtren las claves de esa cuenta de almacenamiento, los atacantes no podrían conectarse a ella para explotar las claves filtradas. Este es otro ejemplo del principio de privilegios mínimos.

Los nodos de un clúster de Azure Kubernetes pueden participar en una red virtual al igual que otros recursos que son más nativos de Azure. Esta funcionalidad se denomina [Interfaz](https://github.com/Azure/azure-container-networking/blob/master/docs/cni.md)de redes de contenedor de Azure . En efecto, asigna una subred dentro de la red virtual en la que se asignan las máquinas virtuales y las imágenes de contenedor.

Continuando por el camino de ilustrar el principio de privilegios mínimos, no todos los recursos dentro de una red virtual necesitan hablar con todos los demás recursos. Por ejemplo, en una aplicación que proporciona una API web a través de una cuenta de almacenamiento y una base de datos SQL, es poco probable que la base de datos y la cuenta de almacenamiento deba hablar entre sí. Cualquier intercambio de datos entre ellos pasaría a través de la aplicación web. Por lo tanto, un grupo de seguridad de [red (NSG)](https://docs.microsoft.com/azure/virtual-network/security-overview) podría utilizarse para denegar el tráfico entre los dos servicios.

Una directiva de denegar la comunicación entre recursos puede ser molesta de implementar, especialmente procedente de un fondo de uso de Azure sin restricciones de tráfico. En algunas otras nubes, el concepto de grupos de seguridad de red es mucho más frecuente. Por ejemplo, la política predeterminada en AWS es que los recursos no pueden comunicarse entre sí hasta que las reglas de un NSG lo habiliten. Aunque es más lento para desarrollar esto, un entorno más restrictivo proporciona un valor predeterminado más seguro. El uso de prácticas de DevOps adecuadas, especialmente mediante [Azure Resource Manager o Terraform](infrastructure-as-code.md) para administrar permisos, puede facilitar el control de las reglas.

Las redes virtuales también pueden ser útiles al configurar la comunicación entre los recursos locales y en la nube. Una red privada virtual se puede utilizar para conectar sin problemas las dos redes juntas. Esto permite ejecutar una red virtual sin ningún tipo de puerta de enlace para escenarios donde todos los usuarios están en el sitio. Hay una serie de tecnologías que se pueden utilizar para establecer esta red. Lo más sencillo es usar una [VPN de sitio a sitio](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-about-vpngateways?toc=%2fazure%2fvirtual-network%2ftoc.json#s2smulti) que se pueda establecer entre muchos enrutadores y Azure. El tráfico se cifra y se tuneliza a través de Internet al mismo costo por byte que cualquier otro tráfico. Para escenarios donde es deseable más ancho de banda o más seguridad, Azure ofrece un servicio denominado [Express Route](https://docs.microsoft.com/azure/vpn-gateway/vpn-gateway-about-vpngateways?toc=%2fazure%2fvirtual-network%2ftoc.json#ExpressRoute) que usa un circuito privado entre una red local y Azure. Es más costoso y difícil de establecer, pero también más seguro.

## <a name="role-based-access-control-for-restricting-access-to-azure-resources"></a>Control de acceso basado en roles para restringir el acceso a los recursos de Azure

RBAC es un sistema que proporciona una identidad a las aplicaciones que se ejecutan en Azure.RBAC es un sistema que proporciona una identidad a las aplicaciones que se ejecutan en Azure.RBAC is a system that provides a identity to applications Las aplicaciones pueden acceder a los recursos mediante esta identidad en lugar de o además de usar claves o contraseñas.

## <a name="security-principals"></a>Entidades de seguridad

El primer componente de RBAC es una entidad de seguridad. Una entidad de seguridad puede ser un usuario, un grupo, una entidad de servicio o una identidad administrada.

![Figura 10-2 Diferentes tipos](./media/rbac-security-principal.png)
de entidades de seguridad**Figura 10-2**. Diferentes tipos de entidades de seguridad.

- Usuario: cualquier usuario que tenga una cuenta en Azure Active Directory es un usuario.
- Grupo: una colección de usuarios de Azure Active Directory. Como miembro de un grupo, un usuario asume los roles de ese grupo además de los suyos.
- Entidad de servicio: una identidad de seguridad bajo la que se ejecutan los servicios o las aplicaciones.
- Identidad administrada: una identidad de Azure Active Directory administrada por Azure. Las identidades administradas se usan normalmente al desarrollar aplicaciones en la nube que administran las credenciales para autenticarse en los servicios de Azure.

La entidad de seguridad se puede aplicar a la mayoría de los recursos. Esto significa que es posible asignar una entidad de seguridad a un contenedor que se ejecuta en Azure Kubernetes, lo que le permite tener acceso a los secretos almacenados en Key Vault. Una función de Azure podría obtener un permiso que le permita hablar con una instancia de Active Directory para validar un JWT para un usuario que realiza la llamada. Una vez que los servicios están habilitados con una entidad de servicio, sus permisos se pueden administrar de forma granular mediante roles y ámbitos.

## <a name="roles"></a>Roles

Un director de seguridad puede asumir muchos roles o, usando una analogía más sartorial, usar muchos sombreros. Cada rol define una serie de permisos como "Leer mensajes desde el punto de conexión de Azure Service Bus". El conjunto de permisos efectivo de una entidad de seguridad es la combinación de todos los permisos asignados a todos los roles que tiene la entidad de seguridad. Azure tiene un gran número de roles integrados y los usuarios pueden definir sus propios roles.

![Figura 10-3 Definiciones](./media/rbac-role-definition.png)
de roles RBAC Figura**10-3**. Definiciones de roles RBAC.

Los roles integrados en Azure también son una serie de roles de alto nivel, como Propietario, Colaborador, Lector y Administrador de cuentas de usuario. Con el rol Propietario, una entidad de seguridad puede tener acceso a todos los recursos y asignar permisos a otros usuarios. Un colaborador tiene el mismo nivel de acceso a todos los recursos, pero no puede asignar permisos. Un lector solo puede ver los recursos de Azure existentes y un administrador de cuentas de usuario puede administrar el acceso a los recursos de Azure.

Los roles integrados más detallados, como [DNS Zone Contributor,](https://docs.microsoft.com/azure/role-based-access-control/built-in-roles#dns-zone-contributor) tienen derechos limitados a un único servicio. Las entidades de seguridad pueden asumir cualquier número de roles.

## <a name="scopes"></a>Ámbitos

Roles can be applied to a restricted set of resources within Azure. Por ejemplo, al aplicar el ámbito al ejemplo anterior de lectura desde una cola de Service Bus, `blah.servicebus.windows.net/queue1`puede restringir el permiso a una sola cola: "Leer mensajes desde el punto de conexión de Azure Service Bus"

El ámbito puede ser tan estrecho como un único recurso o se puede aplicar a todo un grupo de recursos, suscripción o incluso grupo de administración.

Al probar si una entidad de seguridad tiene un permiso determinado, se tiene en cuenta la combinación de rol y ámbito. Esta combinación proporciona un mecanismo de autorización eficaz.

## <a name="deny"></a>Denegar

Anteriormente, solo se permitían reglas de "permitir" para RBAC. Este comportamiento hizo que algunos ámbitos se complican la compilación. Por ejemplo, permitir el acceso de una entidad de seguridad a todas las cuentas de almacenamiento, excepto una necesaria, conceder permiso explícito a una lista potencialmente interminable de cuentas de almacenamiento. Cada vez que se crea una nueva cuenta de almacenamiento, tendría que agregarse a esta lista de cuentas. Esta sobrecarga de administración adicional que, sin duda, no era deseable.

Las reglas de denegación tienen prioridad sobre las reglas de permiso. Ahora representar el mismo alcance de "permitir todos menos uno" podría representarse como dos reglas "permitir todo" y "negar este específico". Denegar reglas no solo facilita la administración, sino que permite recursos que son extra seguros al denegar el acceso a todo el mundo.

## <a name="checking-access"></a>Comprobación del acceso

Como puede imaginar, tener un gran número de roles y ámbitos puede dificultar la determinación del permiso efectivo de una entidad de servicio. Apilamiento negar reglas en la parte superior de eso, sólo sirve para aumentar la complejidad. Afortunadamente, hay una calculadora de permisos que puede mostrar los permisos efectivos para cualquier entidad de servicio. Normalmente se encuentra en la pestaña IAM del portal, como se muestra en la figura 10-3.

![Figura 10-4 Calculadora de](./media/check-rbac.png)
permisos para un servicio de aplicaciones**Figura 10-4**. Calculadora de permisos para un servicio de aplicaciones.

## <a name="securing-secrets"></a>Asegurar secretos

Las contraseñas y los certificados son un vector de ataque común para los atacantes. El hardware de agrietamiento de contraseñas puede hacer un ataque de fuerza bruta e intentar adivinar miles de millones de contraseñas por segundo. Por lo tanto, es importante que las contraseñas que se usan para acceder a los recursos sean fuertes, con una gran variedad de caracteres. Estas contraseñas son exactamente el tipo de contraseñas que son casi imposibles de recordar. Afortunadamente, las contraseñas de Azure no necesitan ser conocidas por ningún humano.

Muchos [expertos](https://www.troyhunt.com/password-managers-dont-have-to-be-perfect-they-just-have-to-be-better-than-not-having-one/) en seguridad sugieren que el mejor enfoque es usar un administrador de contraseñas para mantener sus propias contraseñas. Aunque centraliza las contraseñas en una ubicación, también permite usar contraseñas muy complejas y asegurarse de que son únicas para cada cuenta. El mismo sistema existe en Azure: un almacén central de secretos.

## <a name="azure-key-vault"></a>Azure Key Vault

Azure Key Vault proporciona una ubicación centralizada para almacenar contraseñas para cosas como bases de datos, claves de API y certificados. Una vez que se introduce un secreto en el almacén, nunca se muestra de nuevo y los comandos para extraerlo y verlo son complicados a propósito. La información de la caja fuerte está protegida mediante el cifrado de software o los módulos de seguridad de hardware validados por FIPS 140-2 Nivel 2.

El acceso al almacén de claves se proporciona a través de los RBAC, lo que significa que no cualquier usuario puede acceder a la información del almacén. Supongamos que una aplicación web desea tener acceso a la cadena de conexión de base de datos almacenada en Azure Key Vault. Para obtener acceso, las aplicaciones deben ejecutarse con una entidad de servicio. Bajo este papel asumido, pueden leer los secretos de la caja fuerte. Hay una serie de configuraciones de seguridad diferentes que pueden limitar aún más el acceso que una aplicación tiene al almacén, de modo que no pueda actualizar los secretos, sino solo leerlos.

El acceso al almacén de claves se puede supervisar para asegurarse de que solo las aplicaciones esperadas tienen acceso al almacén. Los registros se pueden volver a integrar en Azure Monitor, desbloqueando la capacidad de configurar alertas cuando se encuentran condiciones inesperadas.

## <a name="kubernetes"></a>Kubernetes

Dentro de Kubernetes, hay un servicio similar para mantener pequeños fragmentos de información secreta. Kubernetes Secrets se puede `kubectl` establecer a través del ejecutable típico.

Crear un secreto es tan simple como encontrar la versión base64 de los valores que se van a almacenar:

```console
echo -n 'admin' | base64
YWRtaW4=
echo -n '1f2d1e2e67df' | base64
MWYyZDFlMmU2N2Rm
```

A continuación, agregándolo `secret.yml` a un archivo de secretos denominado, por ejemplo, que tiene un aspecto similar al ejemplo siguiente:

```yml
apiVersion: v1
kind: Secret
metadata:
  name: mysecret
type: Opaque
data:
  username: YWRtaW4=
  password: MWYyZDFlMmU2N2Rm
```

Por último, este archivo se puede cargar en Kubernetes ejecutando el siguiente comando:

```console
kubectl apply -f ./secret.yaml
```

Estos secretos se pueden montar en volúmenes o exponerse a procesos de contenedor a través de variables de entorno. El enfoque de [aplicación de doce factores](https://12factor.net/) para crear aplicaciones sugiere usar el denominador común más bajo para transmitir la configuración a una aplicación. Las variables de entorno son el denominador común más bajo, ya que son compatibles independientemente del sistema operativo o la aplicación.

Una alternativa para usar los secretos de Kubernetes integrados es tener acceso a los secretos de Azure Key Vault desde Kubernetes. La forma más sencilla de hacerlo es asignar un rol RBAC al contenedor que busca cargar secretos. A continuación, la aplicación puede usar las API de Azure Key Vault para tener acceso a los secretos. Sin embargo, este enfoque requiere modificaciones en el código y no sigue el patrón de uso de variables de entorno. En su lugar, es posible insertar valores en un contenedor mediante el uso de [Azure Key Vault Injector](https://mrdevops.io/introducing-azure-key-vault-to-kubernetes-931f82364354). Este enfoque es en realidad más seguro que el uso de los secretos de Kubernetes directamente, ya que los usuarios del clúster pueden acceder a ellos.

## <a name="encryption-in-transit-and-at-rest"></a>Cifrado en tránsito y en reposo

Mantener los datos seguros es importante tanto si está en disco como si transita entre varios servicios diferentes. La forma más eficaz de evitar que los datos se filtren es cifrarlos en un formato que no pueda ser leído fácilmente por otros. Azure admite una amplia gama de opciones de cifrado.

### <a name="in-transit"></a>En tránsito

Hay varias maneras de cifrar el tráfico en la red en Azure.There are several ways to encrypt traffic on the network in Azure. El acceso a los servicios de Azure se realiza normalmente a través de conexiones que usan Transport Layer Security (TLS). Por ejemplo, todas las conexiones a las API de Azure requieren conexiones TLS. Del mismo modo, las conexiones a puntos de conexión en Azure Storage se pueden restringir para que solo funcionen a través de conexiones cifradas TLS.

TLS es un protocolo complicado y simplemente saber que la conexión está utilizando TLS no es suficiente para garantizar la seguridad. Por ejemplo, TLS 1.0 es crónicamente inseguro y TLS 1.1 no es mucho mejor. Incluso dentro de las versiones de TLS, hay varias configuraciones que pueden hacer que las conexiones sean más fáciles de descifrar. El mejor curso de acción es comprobar y ver si la conexión del servidor está utilizando protocolos actualizados y bien configurados.

Esta comprobación puede ser realizada por un servicio externo como la prueba de servidor SSL de los laboratorios SSL. Una ejecución de prueba en un punto de conexión de Azure típico, en este caso un punto de conexión de bus de servicio, produce una puntuación casi perfecta de A.

Incluso los servicios como las bases de datos SQL de Azure usan el cifrado TLS para mantener los datos ocultos. La parte interesante de cifrar los datos en tránsito mediante TLS es que no es posible, incluso para Microsoft, escuchar en la conexión entre equipos que ejecutan TLS. Esto debería proporcionar comodidad a las empresas interesadas en que sus datos puedan estar en riesgo por parte de Microsoft adecuado o incluso de un actor estatal con más recursos que el atacante estándar.

![Figura 10-5 Informe de laboratorios SSL que muestra una puntuación de A para un punto de conexión de Service Bus. ](./media/ssl-report.png)
 **Figura 10-5**. Informe de laboratorios SSL que muestra una puntuación de A para un punto de conexión de Service Bus.

Aunque este nivel de cifrado no va a ser suficiente para todos los tiempos, debe inspirar confianza en que las conexiones TLS de Azure son bastante seguras. Azure seguirá evolucionando sus estándares de seguridad a medida que mejore el cifrado. Es bueno saber que hay alguien observando los estándares de seguridad y actualizando Azure a medida que mejoran.

### <a name="at-rest"></a>En reposo

En cualquier aplicación, hay una serie de lugares donde los datos descansan en el disco. El propio código de aplicación se carga desde algún mecanismo de almacenamiento. La mayoría de las aplicaciones también usan algún tipo de base de datos, como SQL Server, Cosmos DB o incluso el almacenamiento de tablas increíblemente eficiente. Todas estas bases de datos utilizan almacenamiento fuertemente cifrado para garantizar que nadie más que las aplicaciones con los permisos adecuados pueda leer los datos. Incluso los operadores del sistema no pueden leer los datos cifrados. Para que los clientes puedan mantenerse seguros de que su información secreta permanece secreta.

### <a name="storage"></a>Storage

El fundamento de gran parte de Azure es el motor de Azure Storage. Los discos de máquina virtual se montan encima de Azure Storage. Azure Kubernetes Services se ejecuta en máquinas virtuales que, por sí mismas, se hospedan en Azure Storage. Incluso las tecnologías sin servidor, como Azure Functions Apps e Azure Container Instances, se ejecutan sin disco que forma parte de Azure Storage.

Si Azure Storage está bien cifrado, proporciona una base para que la mayoría de todo lo demás también se cifre. Azure Storage [se cifra](https://docs.microsoft.com/azure/storage/common/storage-service-encryption) con AES de [256 bits](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard)compatible con [FIPS 140-2.](https://en.wikipedia.org/wiki/FIPS_140) Esta es una tecnología de cifrado bien considerada que ha sido objeto de un amplio escrutinio académico en los últimos 20 años. En la actualidad, no hay ningún ataque práctico conocido que permita a alguien sin conocimiento de la clave leer los datos cifrados por AES.

De forma predeterminada, Microsoft administra las claves utilizadas para cifrar Azure Storage. Existen amplias protecciones para garantizar el acceso malintencionado a estas claves. Sin embargo, los usuarios con determinados requisitos de cifrado también pueden [proporcionar sus propias claves](https://docs.microsoft.com/azure/storage/common/storage-encryption-keys-powershell) de almacenamiento que se administran en Azure Key Vault. Estas claves se pueden revocar en cualquier momento, lo que haría que el contenido de la cuenta de almacenamiento las usara inaccesible.

Las máquinas virtuales usan almacenamiento cifrado, pero es posible proporcionar otra capa de cifrado mediante el uso de tecnologías como BitLocker en Windows o DM-Crypt en Linux. Estas tecnologías significan que incluso si la imagen del disco se filtró fuera del almacenamiento, seguiría siendo casi imposible leerla.

### <a name="azure-sql"></a>Azure SQL

Las bases de datos hospedadas en Azure SQL usan una tecnología denominada Cifrado de [datos transparente (TDE)](/sql/relational-databases/security/encryption/transparent-data-encryption) para garantizar que los datos permanezcan cifrados. Está habilitado de forma predeterminada en todas las bases de datos SQL recién creadas, pero debe habilitarse manualmente para las bases de datos heredadas. TDE ejecuta el cifrado y descifrado en tiempo real no solo de la base de datos, sino también de las copias de seguridad y los registros de transacciones.

Los parámetros de `master` cifrado se almacenan en la base de datos y, al iniciarse, se leen en la memoria para las operaciones restantes. Esto significa `master` que la base de datos debe permanecer sin cifrar. Microsoft administra la clave real. Sin embargo, los usuarios con requisitos de seguridad exigentes pueden proporcionar su propia clave en Key Vault de la misma manera que se hace para Azure Storage. Key Vault proporciona servicios como la rotación y la revocación de claves.

La parte "transparente" de TDS proviene del hecho de que no hay cambios de cliente necesarios para usar una base de datos cifrada. Aunque este enfoque proporciona una buena seguridad, la pérdida de la contraseña de la base de datos es suficiente para que los usuarios puedan descifrar los datos. Hay otro enfoque que cifra columnas o tablas individuales en una base de datos. [Always Encrypted](https://docs.microsoft.com/azure/sql-database/sql-database-always-encrypted-azure-key-vault) garantiza que en ningún momento los datos cifrados aparezcan en texto sin formato dentro de la base de datos.

La configuración de este nivel de cifrado requiere que se ejecute a través de un asistente en SQL Server Management StudioSQL Server Management Studio para seleccionar el tipo de cifrado y dónde en Key Vault almacenar las claves asociadas.

![Figura 10-6 Selección de columnas en una](./media/always-encrypted.png)
tabla que se va a cifrar mediante la figura Always Encrypted**10-6**. Selección de columnas en una tabla que se va a cifrar mediante Always Encrypted.

Las aplicaciones cliente que leen información de estas columnas cifradas deben realizar asignaciones especiales para leer los datos cifrados. Las cadenas de conexión `Column Encryption Setting=Enabled` deben actualizarse con las credenciales de cliente y las credenciales de cliente deben recuperarse del almacén de claves. A continuación, el cliente de SQL ServerSQL Server debe estar preparado con las claves de cifrado de columna. Una vez hecho esto, las acciones restantes utilizan las interfaces estándar para SQL Client. Es decir, herramientas como Dapper y Entity Framework, que se basan en SQL Client, seguirán funcionando sin cambios. Es posible que Always Encrypted aún no esté disponible para todos los controladores de SQL Server en todos los idiomas.

La combinación de TDE y Always Encrypted, que se pueden utilizar con claves específicas del cliente, garantiza que se admitan incluso los requisitos de cifrado más exigentes.

### <a name="cosmos-db"></a>Cosmos DB

Cosmos DB es la base de datos más reciente proporcionada por Microsoft en Azure. Se ha construido desde cero con la seguridad y la criptografía en mente. El cifrado AES-256bit es estándar para todas las bases de datos de Cosmos DB y no se puede deshabilitar. Junto con el requisito TLS 1.2 para la comunicación, se cifra toda la solución de almacenamiento.

![Figura 10-7 Flujo de cifrado](./media/cosmos-encryption.png)
de datos dentro de cosmos DB**Figura 10-7**. El flujo de cifrado de datos dentro de Cosmos DB.

Aunque Cosmos DB no proporciona el suministro de claves de cifrado de clientes, el equipo ha realizado un trabajo importante para garantizar que siga siendo compatible con PCI-DSS sin eso. Cosmos DB tampoco admite ningún tipo de cifrado de columna única similar a Always Encrypted de Azure SQL.

## <a name="keeping-secure"></a>Mantenerse seguro

Azure tiene todas las herramientas necesarias para lanzar un producto altamente seguro. Sin embargo, una cadena es tan fuerte como su eslabón más débil. Si las aplicaciones implementadas en la parte superior de Azure no se desarrollan con una mentalidad de seguridad adecuada y buenas auditorías de seguridad, se convierten en el vínculo débil de la cadena. Existen muchas herramientas de análisis estático excelentes, bibliotecas de cifrado y prácticas de seguridad que se pueden usar para garantizar que el software instalado en Azure sea tan seguro como el propio Azure. Entre los ejemplos se incluyen herramientas de [análisis estático,](https://www.whitesourcesoftware.com/)bibliotecas de cifrado y [prácticas](https://www.libressl.org/)de [seguridad.](https://azure.microsoft.com/resources/videos/red-vs-blue-internal-security-penetration-testing-of-microsoft-azure/)

>[!div class="step-by-step"]
>[Anterior](security.md)
>[Siguiente](devops.md)
