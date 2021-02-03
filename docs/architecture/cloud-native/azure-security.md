---
title: Seguridad de Azure para aplicaciones nativas en la nube
description: Diseño de aplicaciones .NET nativas en la nube para Azure | Seguridad de Azure para aplicaciones nativas en la nube
ms.date: 01/19/2021
ms.openlocfilehash: 1e2dce97a43479d49aecf220893efcc19bb00a8c
ms.sourcegitcommit: f2ab02d9a780819ca2e5310bbcf5cfe5b7993041
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "99505887"
---
# <a name="azure-security-for-cloud-native-apps"></a>Seguridad de Azure para aplicaciones nativas en la nube

Las aplicaciones nativas en la nube pueden ser más fáciles y más difíciles de proteger que las aplicaciones tradicionales. En el inconveniente, debe proteger aplicaciones más pequeñas y dedicar más energía a la creación de la infraestructura de seguridad. La naturaleza heterogénea de los lenguajes de programación y los estilos en la mayoría de las implementaciones de servicio también significa que debe prestar más atención a los boletines de seguridad de muchos proveedores diferentes.

En el lado de volteo, los servicios más pequeños, cada uno con su propio almacén de datos, limitan el ámbito de un ataque. Si un atacante pone en peligro un sistema, probablemente sea más difícil para el atacante hacer el salto a otro sistema que en una aplicación monolítica. Los límites de los procesos son límites fuertes. Además, si se expone una copia de seguridad de base de datos, el daño es más limitado, ya que la base de datos solo contiene un subconjunto de datos y es improbable que contenga datos personales.

## <a name="threat-modeling"></a>Modelado de amenazas

Sin importar si las ventajas superan las desventajas de las aplicaciones nativas de la nube, se debe seguir la misma mentalidad holística de seguridad. La seguridad y el pensamiento seguro deben formar parte de cada paso del desarrollo y la historia de las operaciones. Al planear una aplicación, formule preguntas como:

- ¿Cuál sería el impacto de la pérdida de estos datos?
- ¿Cómo podemos limitar el daño de los datos no válidos que se insertan en este servicio?
- ¿Quién debe tener acceso a estos datos?
- ¿Hay directivas de auditoría implementadas en torno al proceso de desarrollo y lanzamiento?

Todas estas preguntas forman parte de un proceso llamado [modelo de amenazas](/azure/security/azure-security-threat-modeling-tool). Este proceso intenta responder a la pregunta de qué amenazas hay en el sistema, la probabilidad de que se trate de las amenazas y los posibles daños que puedan tener.

Una vez establecida la lista de amenazas, debe decidir si merece la pena mitigarla. A veces, una amenaza es tan improbable y costosa de planear que no merece la pena gastar energía en ella. Por ejemplo, algunos actores de nivel de estado pueden insertar cambios en el diseño de un proceso que usan millones de dispositivos. Ahora, en lugar de ejecutar un determinado fragmento de código en el [anillo 3](https://en.wikipedia.org/wiki/Protection_ring), el código se ejecuta en el anillo 0. Este proceso permite una vulnerabilidad que puede omitir el hipervisor y ejecutar el código de ataque en los equipos sin sistema operativo, lo que permite ataques en todas las máquinas virtuales que se ejecutan en ese hardware.

Los procesadores modificados son difíciles de detectar sin un microscopio y conocimientos avanzados del diseño de Silicon del procesador. No es probable que se produzca este escenario y se reduzca el costo, por lo que es probable que no haya ningún modelo de amenazas que recomiende la creación de protección contra vulnerabilidades.

Las amenazas más probables, como los controles de acceso roto que permiten `Id` aumentar los ataques (reemplazando `Id=2` por `Id=3` en la dirección URL) o la inyección de SQL, son más atractivas para la creación de protecciones en. Las mitigaciones de estas amenazas son bastante razonables para compilar y evitar vulnerabilidades de seguridad embarazosas que abven la reputación de la empresa.

## <a name="principle-of-least-privilege"></a>Principio de privilegio mínimo

Una de las ideas de Fundación en la seguridad del equipo es el principio de privilegios mínimos (POLP). En realidad, es una idea fundamental en la mayoría de las formas de seguridad, ya sea digital o física. En Resumen, el principio es que cualquier usuario o proceso debe tener el menor número de derechos posible para ejecutar su tarea.

Como ejemplo, piense en los cajeros de un banco: el acceso a la seguridad es una actividad no habitual. Por lo tanto, el cajero medio no puede abrir la caja de seguridad. Para obtener acceso, deben remitir su solicitud a través de un administrador bancario, que realiza comprobaciones de seguridad adicionales.

En un sistema informático, un ejemplo fantástico son los derechos de un usuario que se conecta a una base de datos. En muchos casos, hay una cuenta de usuario única que se usa para compilar la estructura de base de datos y ejecutar la aplicación. A excepción de los casos extremos, la cuenta que ejecuta la aplicación no necesita la capacidad de actualizar la información del esquema. Debe haber varias cuentas que proporcionen diferentes niveles de privilegios. La aplicación solo debe usar el nivel de permiso que concede acceso de lectura y escritura a los datos de las tablas. Este tipo de protección eliminará los ataques que destinan a quitar tablas de base de datos o a introducir desencadenadores malintencionados.

Casi todas las partes de la creación de una aplicación nativa en la nube pueden beneficiarse de recordar el principio de privilegios mínimos. Puede encontrarla en juego al configurar firewalls, grupos de seguridad de red, roles y ámbitos en el control de acceso basado en rol (RBAC).

## <a name="penetration-testing"></a>Pruebas de penetración

A medida que las aplicaciones se vuelven más complicadas, el número de vectores de ataque aumenta a una velocidad alarmante. El modelado de amenazas tiene un error porque tiende a ser ejecutado por las mismas personas que compilan el sistema. Del mismo modo que muchos desarrolladores tienen problemas para aprovisionar las interacciones del usuario y compilar interfaces de usuario inutilizables, la mayoría de los desarrolladores tienen dificultades para ver todos los vectores de ataque. También es posible que los desarrolladores que compilan el sistema no estén bien desconocidos en las metodologías de ataque y no pierdan algo cruciales.

La prueba de penetración o la "prueba de plumilla" implica la incorporación de actores externos para intentar atacar el sistema. Estos atacantes pueden ser una compañía de consultoría externa u otros desarrolladores con buenos conocimientos de seguridad de otra parte de la empresa. Se les asigna blanca para intentar deshacer el sistema. Con frecuencia, encontrará extensos agujeros de seguridad que deben revisarse. A veces, el vector de ataque será algo totalmente inesperado, como aprovechar un ataque de suplantación de identidad contra el CEO.

Azure en sí está realizando continuamente ataques de un [equipo de hackers dentro de Microsoft](https://azure.microsoft.com/resources/videos/red-vs-blue-internal-security-penetration-testing-of-microsoft-azure/). A lo largo de los años, han sido el primero en encontrar docenas de vectores de ataque potencialmente catastróficos, y cerrarlos antes de que se puedan aprovechar externamente. Cuanto más tentador sea el destino, más probable es que los actores de infinitas intenten aprovecharlo y que hay algunos destinos en el mundo más tentados que Azure.

## <a name="monitoring"></a>Supervisión

En caso de que un atacante intente penetrar en una aplicación, debería haber alguna advertencia. Con frecuencia, los ataques se pueden detectar examinando los registros de los servicios. Los ataques dejan signos testigo que se pueden detectar antes de que se realicen correctamente. Por ejemplo, un atacante que intente adivinar una contraseña realizará muchas solicitudes a un sistema de inicio de sesión. La supervisión alrededor del sistema de inicio de sesión puede detectar patrones extraños que no están en línea con el patrón de acceso típico. Esta supervisión se puede convertir en una alerta que, a su vez, alerta a una persona de operaciones para activar algún tipo de contramedida. Un sistema de supervisión muy maduro podría incluso actuar en función de estas desviaciones agregando de forma proactiva reglas para bloquear solicitudes o limitar las respuestas.

## <a name="securing-the-build"></a>Proteger la compilación

Un lugar en el que se suele pasar por alto la seguridad está en torno al proceso de compilación. La compilación no solo debe ejecutar comprobaciones de seguridad, como el análisis de código no seguro ni credenciales protegidas, pero la propia compilación debe ser segura. Si el servidor de compilación está en peligro, proporciona un vector fantástico para introducir código arbitrario en el producto.

Imagine que un atacante está intentando robar las contraseñas de los usuarios que inician sesión en una aplicación Web. Podrían introducir un paso de compilación que modifica el código desprotegido para reflejar cualquier solicitud de inicio de sesión en otro servidor. La próxima vez que el código pase por la compilación, se actualizará de forma silenciosa. El examen de vulnerabilidades del código fuente no detectará esta vulnerabilidad mientras se ejecuta antes de la compilación. Del mismo modo, nadie lo detectará en una revisión de código, ya que los pasos de compilación se activan en el servidor de compilación. El código aprovechado irá a producción en la que puede recopilar contraseñas. Probablemente no haya ningún registro de auditoría de los cambios realizados en el proceso de compilación, o al menos nadie supervisando la auditoría.

Este escenario es un ejemplo perfecto de un destino aparentemente de valor bajo que se puede utilizar para interrumpir el sistema. Una vez que un atacante infringe el perímetro del sistema, puede empezar a trabajar en la búsqueda de maneras de elevar sus permisos hasta el punto en el que pueden causar daños reales en cualquier lugar en el que quieran.

## <a name="building-secure-code"></a>Compilar código seguro

.NET Framework ya es un marco bastante seguro. Evita algunos de los problemas de código no administrado, como recorrer los extremos de las matrices. El trabajo se realiza activamente para corregir las carencias de seguridad a medida que se detectan. Hay incluso un [programa de recompensa de errores](https://www.microsoft.com/msrc/bounty) que paga a los investigadores a encontrar problemas en el marco y notificarlos en lugar de aprovecharlos.

Hay muchas maneras de hacer que el código .NET sea más seguro. Las instrucciones siguientes, como el artículo [instrucciones de codificación segura para .net](../../standard/security/secure-coding-guidelines.md) , son un paso razonable para asegurarse de que el código es seguro desde el principio. [OWASP Top 10](https://owasp.org/www-project-top-ten/) es otra guía valiosa para compilar código seguro.

El proceso de compilación es un buen lugar para colocar herramientas de detección para detectar problemas en el código fuente antes de que se pongan en producción. La mayoría de los proyectos tiene dependencias en otros paquetes. Una herramienta que puede buscar paquetes obsoletos detectará problemas en una compilación nocturna. Incluso al crear imágenes de Docker, es útil comprobar y asegurarse de que la imagen base no tiene vulnerabilidades conocidas. Otro aspecto que hay que comprobar es que nadie ha protegido accidentalmente las credenciales.

## <a name="built-in-security"></a>Seguridad integrada

Azure está diseñado para equilibrar la facilidad de uso y la seguridad de la mayoría de los usuarios. Los distintos usuarios van a tener distintos requisitos de seguridad, por lo que necesitan ajustar su enfoque a la seguridad en la nube. Microsoft publica una gran cantidad de información de seguridad en el [centro de confianza](https://azure.microsoft.com/support/trust-center/). Este recurso debe ser el primero en los profesionales interesados en comprender cómo funcionan las tecnologías integradas de mitigación de ataques.

Dentro del Azure Portal, el [Azure Advisor](https://azure.microsoft.com/services/advisor/) es un sistema que está explorando un entorno constantemente y realizando recomendaciones. Algunas de estas recomendaciones están diseñadas para ahorrar dinero a los usuarios, pero otras están diseñadas para identificar configuraciones potencialmente inseguras, como tener un contenedor de almacenamiento abierto al mundo y no estar protegido por un Virtual Network.

## <a name="azure-network-infrastructure"></a>Infraestructura de red de Azure

En un entorno de implementación local, una gran cantidad de energía está dedicada a la configuración de redes. La configuración de enrutadores, conmutadores y el tipo de trabajo es complicado. Las redes permiten determinados recursos para comunicarse con otros recursos y evitar el acceso en algunos casos. Una regla de red frecuente es restringir el acceso al entorno de producción desde el entorno de desarrollo sin que sea posible que un fragmento de código de uso medio se ejecute mal y elimine un montón de datos.

Desde el cuadro, la mayoría de los recursos de Azure PaaS solo tienen la configuración de redes más básica y permisiva. Por ejemplo, cualquier persona en Internet puede acceder a una instancia de App Service. Las instancias de SQL Server nuevas suelen estar restringidas, por lo que las entidades externas no pueden tener acceso a ellas, pero se permiten los intervalos de direcciones IP que usa Azure. Por lo tanto, mientras el servidor SQL Server está protegido contra amenazas externas, un atacante solo necesita configurar un servidor cabeza de puente de Azure desde donde puedan lanzar ataques contra todas las instancias de SQL en Azure.

Afortunadamente, la mayoría de los recursos de Azure se pueden colocar en una Virtual Network de Azure que permita un control de acceso específico. De forma similar a la manera en que las redes locales establecen redes privadas que están protegidas del mundo más amplio, las redes virtuales son islas de direcciones IP privadas que se encuentran en la red de Azure.

![Figura 9-1 una red virtual en Azure](./media/virtual-network.png)

**Figura 9-1**. Una red virtual en Azure.

Del mismo modo que las redes locales tienen un firewall que rige el acceso a la red, puede establecer un firewall similar en el límite de la red virtual. De forma predeterminada, todos los recursos de una red virtual pueden seguir hablando con Internet. Solo son conexiones entrantes que requieren algún tipo de excepción explícita del firewall.

Con la red establecida, los recursos internos, como las cuentas de almacenamiento, pueden configurarse para permitir solo el acceso a los recursos que también se encuentran en el Virtual Network. Este firewall proporciona un nivel de seguridad adicional, en caso de que se pierdan las claves de esa cuenta de almacenamiento, los atacantes no podrán conectarse a ella para aprovechar las claves perdidas. Este escenario es otro ejemplo del principio de privilegios mínimos.

Los nodos de un clúster de Azure Kubernetes pueden participar en una red virtual, al igual que otros recursos que son más nativos de Azure. Esta funcionalidad se denomina [interfaz de red de contenedor de Azure](https://github.com/Azure/azure-container-networking/blob/master/docs/cni.md). De hecho, asigna una subred dentro de la red virtual en la que se asignan las máquinas virtuales y las imágenes de contenedor.

Al continuar con la ruta de acceso que ilustra el principio de privilegios mínimos, no todos los recursos de una Virtual Network deben comunicarse con los demás recursos. Por ejemplo, en una aplicación que proporciona una API Web a través de una cuenta de almacenamiento y una base de datos SQL, es poco probable que la base de datos y la cuenta de almacenamiento deban comunicarse entre sí. Cualquier uso compartido de datos entre ellos pasará a través de la aplicación Web. Por lo tanto, se puede usar un [grupo de seguridad de red (NSG)](/azure/virtual-network/security-overview) para denegar el tráfico entre los dos servicios.

Una directiva de denegación de la comunicación entre los recursos puede resultar molesta de implementar, especialmente desde un segundo plano sobre el uso de Azure sin restricciones de tráfico. En algunas otras nubes, el concepto de grupos de seguridad de red es mucho más frecuente. Por ejemplo, la directiva predeterminada en AWS es que los recursos no se pueden comunicar entre ellos hasta que las reglas de un NSG lo habilitan. Aunque es más lento desarrollar esto, un entorno más restrictivo proporciona un valor predeterminado más seguro. El uso de prácticas de DevOps adecuadas, especialmente el uso de [Azure Resource Manager o terraform](infrastructure-as-code.md) para administrar permisos puede facilitar el control de las reglas.

Las redes virtuales también pueden ser útiles al configurar la comunicación entre los recursos locales y en la nube. Una red privada virtual se puede usar para conectar las dos redes sin problemas. Este enfoque permite ejecutar una red virtual sin ningún tipo de puerta de enlace para los escenarios en los que todos los usuarios están en el sitio. Hay una serie de tecnologías que se pueden usar para establecer esta red. La más sencilla es usar una [VPN de sitio a sitio](/azure/vpn-gateway/vpn-gateway-about-vpngateways?toc=%252fazure%252fvirtual-network%252ftoc.json#s2smulti) que se puede establecer entre varios enrutadores y Azure. El tráfico se cifra y se tuneliza por Internet con el mismo costo por byte que cualquier otro tráfico. En escenarios donde se desea más ancho de banda o más seguridad, Azure ofrece un [servicio denominado expressroute](/azure/vpn-gateway/vpn-gateway-about-vpngateways?toc=%252fazure%252fvirtual-network%252ftoc.json#ExpressRoute) que usa un circuito privado entre una red local y Azure. Es más costosa y difícil de establecer, pero también más seguro.

## <a name="role-based-access-control-for-restricting-access-to-azure-resources"></a>Control de acceso basado en roles para restringir el acceso a los recursos de Azure

RBAC es un sistema que proporciona una identidad a las aplicaciones que se ejecutan en Azure. Las aplicaciones pueden tener acceso a los recursos que usan esta identidad en lugar de usar claves o contraseñas.

## <a name="security-principals"></a>Entidades de seguridad

El primer componente de RBAC es una entidad de seguridad. Una entidad de seguridad puede ser un usuario, un grupo, una entidad de servicio o una identidad administrada.

![Figura 9-2 distintos tipos de entidades de seguridad](./media/rbac-security-principal.png)

**Figura 9-2**. Distintos tipos de entidades de seguridad.

- Usuario: cualquier usuario que tenga una cuenta en Azure Active Directory es un usuario.
- Grupo: una colección de usuarios de Azure Active Directory. Como miembro de un grupo, un usuario toma los roles de ese grupo además de los suyos propios.
- Entidad de servicio: identidad de seguridad en la que se ejecutan los servicios o las aplicaciones.
- Identidad administrada: identidad de Azure Active Directory administrada por Azure. Las identidades administradas se utilizan normalmente al desarrollar aplicaciones en la nube que administran las credenciales para autenticarse en los servicios de Azure.

La entidad de seguridad se puede aplicar a la mayoría de los recursos. Este aspecto significa que es posible asignar una entidad de seguridad a un contenedor que se ejecuta dentro de Azure Kubernetes, lo que le permite acceder a los secretos almacenados en Key Vault. Una función de Azure puede asumir un permiso que le permite comunicarse con una instancia de Active Directory para validar un JWT para un usuario que realiza la llamada. Una vez que los servicios se habilitan con una entidad de servicio, sus permisos se pueden administrar granularmente mediante roles y ámbitos.

## <a name="roles"></a>Roles

Una entidad de seguridad puede asumir muchos roles o, con una analogía más sartorial, gastar muchos sombreros. Cada rol define una serie de permisos, como "leer mensajes de Azure Service Bus punto de conexión". El conjunto de permisos efectivo de una entidad de seguridad es la combinación de todos los permisos asignados a todos los roles que tiene una entidad de seguridad. Azure tiene un gran número de roles integrados y los usuarios pueden definir sus propios roles.

![Figura 9-3 definiciones de roles RBAC](./media/rbac-role-definition.png)

**Figura 9-3**. Definiciones de roles de RBAC.

Integrado en Azure también son una serie de roles de alto nivel, como propietario, colaborador, lector y administrador de cuentas de usuario. Con el rol de propietario, una entidad de seguridad puede tener acceso a todos los recursos y asignar permisos a otros usuarios. Un colaborador tiene el mismo nivel de acceso a todos los recursos, pero no puede asignar permisos. Un lector solo puede ver los recursos de Azure existentes y un administrador de cuentas de usuario puede administrar el acceso a los recursos de Azure.

Los roles integrados más granulares, como el [colaborador de zona DNS](/azure/role-based-access-control/built-in-roles#dns-zone-contributor) , tienen derechos limitados a un único servicio. Las entidades de seguridad pueden tomar cualquier número de roles.

## <a name="scopes"></a>Ámbitos

Los roles se pueden aplicar a un conjunto restringido de recursos dentro de Azure. Por ejemplo, al aplicar el ámbito al ejemplo anterior de lectura desde una cola de Service Bus, puede restringir el permiso a una sola cola: "leer mensajes de un punto de conexión de Azure Service Bus `blah.servicebus.windows.net/queue1` ".

El ámbito puede ser tan estrecho como un recurso único o se puede aplicar a un grupo de recursos completo, una suscripción o incluso un grupo de administración.

Al probar si una entidad de seguridad tiene determinados permisos, se tiene en cuenta la combinación de rol y ámbito. Esta combinación proporciona un mecanismo de autorización eficaz.

## <a name="deny"></a>Denegar

Anteriormente, solo se permitían las reglas de "permitir" para RBAC. Este comportamiento hace que algunos ámbitos sean complicados de compilar. Por ejemplo, permitir que una entidad de seguridad tenga acceso a todas las cuentas de almacenamiento, salvo que se requiera conceder permisos explícitos a una lista de cuentas de almacenamiento potencialmente ilimitada. Cada vez que se crea una nueva cuenta de almacenamiento, debe agregarse a esta lista de cuentas. Esta sobrecarga de administración agregada sin duda.

Las reglas de denegación tienen prioridad sobre las reglas de permiso. Ahora que representa el mismo ámbito "permitir todo menos uno" se puede representar como dos reglas "permitir todo" y "denegar esta una específica". Las reglas de denegación no solo facilitan la administración, sino que permiten que los recursos sean más seguros al denegar el acceso a todos.

## <a name="checking-access"></a>Comprobando el acceso

Como puede imaginar, tener un gran número de roles y ámbitos puede hacer que la determinancia del permiso efectivo de una entidad de servicio sea bastante difícil. Apilar las reglas de denegación en la parte superior, solo sirve para aumentar la complejidad. Afortunadamente, hay una [calculadora de permisos](/azure/role-based-access-control/check-access) que puede mostrar los permisos efectivos de cualquier entidad de servicio. Normalmente se encuentra en la pestaña IAM del portal, como se muestra en la figura 9-3.

![Figura 9-4 calculadora de permisos para una aplicación de App Service](./media/check-rbac.png)

**Figura 9-4**. Calculadora de permisos para una aplicación de App Service.

## <a name="securing-secrets"></a>Protección de secretos

Las contraseñas y los certificados son un vector de ataque común para los atacantes. El hardware de averiguación de contraseñas puede realizar un ataque por fuerza bruta e intentar adivinar miles de millones de contraseñas por segundo. Por lo tanto, es importante que las contraseñas que se usan para tener acceso a los recursos sean seguras, con una gran variedad de caracteres. Estas contraseñas son exactamente el tipo de contraseñas que son casi imposibles de recordar. Afortunadamente, las contraseñas de Azure no necesitan ser conocidas por ningún usuario.

Muchos expertos en seguridad [sugieren](https://www.troyhunt.com/password-managers-dont-have-to-be-perfect-they-just-have-to-be-better-than-not-having-one/) que el uso de un administrador de contraseñas para mantener sus propias contraseñas es el mejor enfoque. Aunque centraliza las contraseñas en una ubicación, también permite usar contraseñas muy complejas y asegurarse de que son únicas para cada cuenta. El mismo sistema existe en Azure: un almacén central de secretos.

## <a name="azure-key-vault"></a>Azure Key Vault

Azure Key Vault proporciona una ubicación centralizada para almacenar las contraseñas de elementos como bases de datos, claves de API y certificados. Una vez que se introduce un secreto en el almacén, nunca se vuelve a mostrar y los comandos para extraer y ver son complicados. La información contenida en Safe está protegida mediante el cifrado de software o los módulos de seguridad de hardware validados de nivel 2 de FIPS 140-2.

El acceso al almacén de claves se proporciona a través de RBACs, lo que significa que no solo cualquier usuario puede acceder a la información del almacén. Suponga que una aplicación web desea tener acceso a la cadena de conexión de base de datos almacenada en Azure Key Vault. Para obtener acceso, las aplicaciones deben ejecutarse con una entidad de servicio. En este rol asumido, pueden leer los secretos de la caja de seguridad. Hay una serie de opciones de configuración de seguridad diferentes que pueden limitar aún más el acceso que tiene una aplicación al almacén, de modo que no pueda actualizar los secretos pero solo leerlos.

Se puede supervisar el acceso al almacén de claves para asegurarse de que solo las aplicaciones esperadas tengan acceso al almacén. Los registros se pueden volver a integrar en Azure Monitor, desbloqueando la capacidad de configurar alertas cuando se encuentran condiciones inesperadas.

## <a name="kubernetes"></a>Kubernetes

Dentro de Kubernetes, hay un servicio similar para mantener pequeños fragmentos de información secreta. Los secretos de Kubernetes se pueden establecer mediante el `kubectl` ejecutable típico.

Crear un secreto es tan sencillo como encontrar la versión de Base64 de los valores que se van a almacenar:

```console
echo -n 'admin' | base64
YWRtaW4=
echo -n '1f2d1e2e67df' | base64
MWYyZDFlMmU2N2Rm
```

A continuación, agréguelo a un archivo de secretos denominado, por ejemplo, con un `secret.yml` aspecto similar al ejemplo siguiente:

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

Por último, este archivo se puede cargar en Kubernetes ejecutando el comando siguiente:

```console
kubectl apply -f ./secret.yaml
```

Estos secretos se pueden montar en volúmenes o exponerse a los procesos de contenedor mediante variables de entorno. El enfoque de [aplicación de doce factores](https://12factor.net/) para la creación de aplicaciones sugiere el uso del denominador común más bajo para transmitir la configuración a una aplicación. Las variables de entorno son el denominador común más bajo, ya que se admiten independientemente del sistema operativo o de la aplicación.

Una alternativa a usar los secretos de Kubernetes integrados es acceder a los secretos en Azure Key Vault desde Kubernetes. La manera más sencilla de hacerlo es asignar un rol de RBAC al contenedor que quiera cargar los secretos. A continuación, la aplicación puede usar las API de Azure Key Vault para tener acceso a los secretos. Sin embargo, este enfoque requiere modificaciones en el código y no sigue el patrón de uso de variables de entorno. En su lugar, es posible insertar valores en un contenedor. Este enfoque es realmente más seguro que usar los secretos de Kubernetes directamente, ya que los usuarios pueden tener acceso a ellos en el clúster.

## <a name="encryption-in-transit-and-at-rest"></a>Cifrado en tránsito y en reposo

Mantener la seguridad de los datos es importante tanto si se encuentra en el disco como si está en tránsito entre distintos servicios. La forma más eficaz de evitar la pérdida de datos es cifrarla en un formato que otros usuarios no puedan leer con facilidad. Azure admite una amplia gama de opciones de cifrado.

### <a name="in-transit"></a>En tránsito

Hay varias maneras de cifrar el tráfico en la red en Azure. Normalmente, el acceso a los servicios de Azure se realiza a través de las conexiones que usan la seguridad de la capa de transporte (TLS). Por ejemplo, todas las conexiones a las API de Azure requieren conexiones TLS. Del mismo modo, las conexiones a los puntos de conexión de Azure Storage se pueden restringir para que solo funcionen con conexiones cifradas TLS.

TLS es un protocolo complicado y solo sabe que la conexión está usando TLS no es suficiente para garantizar la seguridad. Por ejemplo, TLS 1,0 es crónicomente inseguro y TLS 1,1 no es mucho mejor. Incluso dentro de las versiones de TLS, hay varias configuraciones que pueden facilitar el descifrado de las conexiones. La mejor opción consiste en comprobar y ver si la conexión del servidor usa protocolos actualizados y bien configurados.

Esta comprobación se puede realizar mediante un servicio externo, como la prueba de servidor SSL de los laboratorios SSL. Una ejecución de pruebas en un punto de conexión de Azure típico, en este caso un punto de conexión de Service Bus, produce una puntuación casi perfecta de.

Incluso los servicios como las bases de datos SQL de Azure usan cifrado TLS para mantener los datos ocultos. La parte interesante sobre el cifrado de los datos en tránsito mediante TLS es que no es posible, incluso para Microsoft, escuchar en la conexión entre equipos que ejecutan TLS. Esto debe aportar la comodidad a las empresas interesadas en que sus datos pueden estar en riesgo de ser adecuados para Microsoft o incluso un actor de estado con más recursos que el atacante estándar.

![Figura 9-5 Informe de laboratorios de SSL que muestra la puntuación de un para un punto de conexión de Service Bus.](./media/ssl-report.png)

**Figura 9-5**. Informe de laboratorios de SSL que muestra una puntuación de un para un punto de conexión de Service Bus.

Aunque este nivel de cifrado no va a ser suficiente para todo el tiempo, debe inspirar confianza a que las conexiones TLS de Azure son bastante seguras. Azure seguirá evolucionando sus estándares de seguridad a medida que el cifrado mejora. Es interesante saber que hay alguien viendo los estándares de seguridad y actualizando Azure a medida que mejoran.

### <a name="at-rest"></a>En reposo

En cualquier aplicación, hay una serie de lugares en los que los datos se encuentran en el disco. El propio código de aplicación se carga desde algún mecanismo de almacenamiento. La mayoría de las aplicaciones también utilizan algún tipo de base de datos, como SQL Server, Cosmos DB o incluso el Table Storage sorprendentemente eficaz. Todas estas bases de datos usan almacenamiento de gran cifrado para asegurarse de que nadie distinto de las aplicaciones con los permisos adecuados puede leer los datos. Incluso los operadores del sistema no pueden leer los datos que se han cifrado. Así, los clientes pueden estar seguros de que la información secreta sigue siendo secreta.

### <a name="storage"></a>Storage

La subyacente de gran parte de Azure es el motor de Azure Storage. Los discos de máquina virtual se montan encima de Azure Storage. Azure Kubernetes Service se ejecuta en máquinas virtuales que, a su vez, se hospedan en Azure Storage. Incluso las tecnologías sin servidor, como Azure Functions aplicaciones y Azure Container Instances, se ejecutan fuera del disco que forma parte de Azure Storage.

Si Azure Storage está bien cifrado, proporciona una base para la mayoría de los demás que también se cifren. Azure Storage [está cifrado](/azure/storage/common/storage-service-encryption) con la [norma FIPS 140-2](https://en.wikipedia.org/wiki/FIPS_140) compatible con [AES de 256 bits](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard). Se trata de una tecnología de cifrado bien considerada que ha sido el asunto de un amplio examen académico en los últimos 20 años. En la actualidad, no hay ningún ataque práctico conocido que permita a alguien sin conocimiento de la clave leer los datos cifrados con AES.

De forma predeterminada, Microsoft administra las claves utilizadas para cifrar Azure Storage. Existen amplias protecciones para garantizar la prevención del acceso malintencionado a estas claves. Sin embargo, los usuarios con determinados requisitos de cifrado también pueden [proporcionar sus propias claves de almacenamiento](/azure/storage/common/storage-encryption-keys-powershell) que se administran en Azure Key Vault. Estas claves se pueden revocar en cualquier momento, lo que representaría de forma eficaz el contenido de la cuenta de almacenamiento mediante el acceso no accesible.

Las máquinas virtuales usan almacenamiento cifrado, pero es posible proporcionar otra capa de cifrado mediante tecnologías como BitLocker en Windows o DM-Crypt en Linux. Estas tecnologías significan que incluso si la imagen de disco se perdió fuera del almacenamiento, no sería posible leerla.

### <a name="azure-sql"></a>Azure SQL

Las bases de datos hospedadas en SQL de Azure usan una tecnología denominada [cifrado de datos transparente (TDE)](/sql/relational-databases/security/encryption/transparent-data-encryption) para asegurarse de que los datos permanecen cifrados. Está habilitada de forma predeterminada en todas las bases de datos SQL recién creadas, pero debe habilitarse manualmente para las bases de datos heredadas. TDE ejecuta el cifrado y descifrado en tiempo real de no solo la base de datos, sino también las copias de seguridad y los registros de transacciones.

Los parámetros de cifrado se almacenan en la `master` base de datos y, en el inicio, se leen en la memoria para las operaciones restantes. Esto significa que la `master` base de datos debe permanecer sin cifrar. La clave real es administrada por Microsoft. Sin embargo, los usuarios con los requisitos de seguridad de peractuación pueden proporcionar su propia clave en Key Vault de forma muy similar a como se hace en Azure Storage. La Key Vault proporciona para tales servicios como la revocación y la rotación de claves.

La parte "transparente" de TDS procede del hecho de que no se necesitan cambios en el cliente para utilizar una base de datos cifrada. Aunque este enfoque proporciona una buena seguridad, la pérdida de la contraseña de la base de datos es suficiente para que los usuarios puedan descifrar los datos. Hay otro enfoque que cifra columnas o tablas individuales en una base de datos. [Always Encrypted](/azure/sql-database/sql-database-always-encrypted-azure-key-vault) garantiza que en ningún momento los datos cifrados aparecen en texto sin formato dentro de la base de datos.

La configuración de este nivel de cifrado requiere que se ejecute a través de un asistente en SQL Server Management Studio para seleccionar el tipo de cifrado y en Key Vault para almacenar las claves asociadas.

![Figura 9-6 selección de las columnas de una tabla que se van a cifrar con Always Encrypted](./media/always-encrypted.png)

**Figura 9-6**. Seleccionar las columnas de una tabla que se van a cifrar mediante Always Encrypted.

Las aplicaciones cliente que leen la información de estas columnas cifradas deben tomar provisiones especiales para leer los datos cifrados. Las cadenas de conexión deben actualizarse con `Column Encryption Setting=Enabled` y las credenciales del cliente se deben recuperar del Key Vault. A continuación, el cliente de SQL Server debe estar injunto con las claves de cifrado de columna. Una vez hecho esto, las acciones restantes usan las interfaces estándar para el cliente SQL. Es decir, herramientas como Dapper y Entity Framework, que se basan en SQL Client, seguirán funcionando sin cambios. Es posible que Always Encrypted todavía no esté disponible para cada controlador de SQL Server en todos los idiomas.

La combinación de TDE y Always Encrypted, que se pueden usar con claves específicas del cliente, garantiza que se admiten incluso los requisitos de cifrado más inactivos.

### <a name="cosmos-db"></a>Cosmos DB

Cosmos DB es la base de datos más reciente proporcionada por Microsoft en Azure. Se ha creado desde el principio con la seguridad y la criptografía en mente. El cifrado AES-256bit es estándar para todas las bases de datos de Cosmos DB y no se puede deshabilitar. Junto con el requisito de TLS 1,2 para la comunicación, se cifra toda la solución de almacenamiento.

![Figura 9-7 el flujo del cifrado de datos dentro de Cosmos DB](./media/cosmos-encryption.png)

**Figura 9-7**. El flujo de cifrado de datos dentro de Cosmos DB.

Aunque Cosmos DB no proporciona claves de cifrado de cliente, ha habido un trabajo importante realizado por el equipo para asegurarse de que sigue siendo compatible con PCI-DSS sin eso. Cosmos DB tampoco admite todavía ningún tipo de cifrado de una sola columna similar a la Always Encrypted de Azure SQL.

## <a name="keeping-secure"></a>Mantener la seguridad

Azure tiene todas las herramientas necesarias para publicar un producto de alta seguridad. Sin embargo, una cadena es tan segura como su vínculo más débil. Si las aplicaciones implementadas sobre Azure no se desarrollan con una mentalidad de seguridad adecuada y auditorías de seguridad adecuadas, se convierten en el vínculo débil de la cadena. Hay muchas excelentes herramientas de análisis estático, bibliotecas de cifrado y prácticas de seguridad que se pueden usar para asegurarse de que el software instalado en Azure es tan seguro como el propio Azure. Entre los ejemplos se incluyen [herramientas de análisis estático](https://www.whitesourcesoftware.com/), [bibliotecas de cifrado](https://www.libressl.org/)y [prácticas de seguridad](https://azure.microsoft.com/resources/videos/red-vs-blue-internal-security-penetration-testing-of-microsoft-azure/).

>[!div class="step-by-step"]
>[Anterior](security.md)
>[Siguiente](devops.md)
