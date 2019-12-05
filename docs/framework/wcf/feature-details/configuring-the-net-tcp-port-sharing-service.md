---
title: Configuración del servicio de uso compartido de puertos Net.TCP
ms.date: 03/30/2017
ms.assetid: b6dd81fa-68b7-4e1b-868e-88e5901b7ea0
ms.openlocfilehash: 2ff622dc97e63bd0ee10f00c7515692be8df09a1
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837459"
---
# <a name="configuring-the-nettcp-port-sharing-service"></a><span data-ttu-id="1b9e9-102">Configuración del servicio de uso compartido de puertos Net.TCP</span><span class="sxs-lookup"><span data-stu-id="1b9e9-102">Configuring the Net.TCP Port Sharing Service</span></span>
<span data-ttu-id="1b9e9-103">Los servicios autohospedados que utilizan el transporte Net.TCP pueden controlar varios ajustes avanzados, como `ListenBacklog` y `MaxPendingAccepts`, que rigen el comportamiento del socket de TCP subyacente utilizado para la comunicación por red.</span><span class="sxs-lookup"><span data-stu-id="1b9e9-103">Self-hosted services that use the Net.TCP transport can control several advanced settings, such as `ListenBacklog` and `MaxPendingAccepts`, which govern the behavior of the underlying TCP socket used for network communication.</span></span> <span data-ttu-id="1b9e9-104">Sin embargo, esta configuración para cada socket solo se aplica en el nivel de enlace si el enlace de transporte ha deshabilitado el uso compartido de puertos, que está habilitado de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1b9e9-104">However, these settings for each socket only apply at the binding level if the transport binding has disabled port sharing, which is enabled by default.</span></span>  
  
 <span data-ttu-id="1b9e9-105">Cuando un enlace net.tcp habilita el uso compartido de puertos (estableciendo `portSharingEnabled =true` en el elemento de enlace de transporte), permite implícitamente a un proceso externo (concretamente SMSvcHost.exe, que hospeda el servicio de uso compartido de puertos Net.TCP) que administre el socket TCP en su nombre.</span><span class="sxs-lookup"><span data-stu-id="1b9e9-105">When a net.tcp binding enables port sharing (by setting `portSharingEnabled =true` on the transport binding element), it implicitly allows an external process (namely the SMSvcHost.exe, which hosts the Net.TCP Port Sharing Service) to manage the TCP socket on its behalf.</span></span> <span data-ttu-id="1b9e9-106">Por ejemplo, al utilizar TCP, especifique:</span><span class="sxs-lookup"><span data-stu-id="1b9e9-106">For example, when using TCP, specify:</span></span>  
  
```xml  
<tcpTransport portSharingEnabled="true"  />  
```  
  
 <span data-ttu-id="1b9e9-107">Cuando se configura de esta manera, los valores de socket especificados en el elemento de enlace de transporte del servicio se omiten a favor de los valores de socket especificados por SMSvcHost.exe.</span><span class="sxs-lookup"><span data-stu-id="1b9e9-107">When configured in this way, any socket settings specified on the service's transport binding element are ignored in favor of the socket settings specified by SMSvcHost.exe.</span></span>  
  
 <span data-ttu-id="1b9e9-108">Para configurar SMSvcHost.exe, cree un archivo de configuración XML denominado SmSvcHost.exe.config y colóquelo en el mismo directorio físico que el archivo ejecutable SMSvcHost.exe (por ejemplo, C:\Windows\Microsoft.NET\Framework\v4.5).</span><span class="sxs-lookup"><span data-stu-id="1b9e9-108">To configure the SMSvcHost.exe, create an XML configuration file named SmSvcHost.exe.config and place it in the same physical directory as the SMSvcHost.exe executable (for example, C:\Windows\Microsoft.NET\Framework\v4.5).</span></span>  
  
 <span data-ttu-id="1b9e9-109">El siguiente ejemplo muestra un SMSvcHost.exe.config de ejemplo, con la configuración predeterminada de todos los valores configurables declarados explícitamente.</span><span class="sxs-lookup"><span data-stu-id="1b9e9-109">The following example illustrates a sample SMSvcHost.exe.config, with the default settings for all configurable values stated explicitly.</span></span>  
  
```xml  
<configuration>  
   <system.serviceModel.activation>  
       <net.tcp listenBacklog="16" <!--16 * # of processors -->  
          maxPendingAccepts="4"<!-- 4 * # of processors -->  
          maxPendingConnections="100"  
          receiveTimeout="00:00:30" <!--30 seconds -->  
          teredoEnabled="false">  
          <allowAccounts>  
             <!-- LocalSystem account -->  
             <add securityIdentifier="S-1-5-18"/>  
             <!-- LocalService account -->  
             <add securityIdentifier="S-1-5-19"/>  
             <!-- Administrators account -->  
             <add securityIdentifier="S-1-5-20"/>  
             <!-- Network Service account -->  
             <add securityIdentifier="S-1-5-32-544" />  
             <!-- IIS_IUSRS account (Vista only) -->  
             <add securityIdentifier="S-1-5-32-568"/>  
           </allowAccounts>  
       </net.tcp>  
</configuration>  
```  
  
## <a name="when-to-modify-smsvchostexeconfig"></a><span data-ttu-id="1b9e9-110">Cuándo modificar SMSvcHost.exe.config</span><span class="sxs-lookup"><span data-stu-id="1b9e9-110">When to Modify SMSvcHost.exe.config</span></span>  
 <span data-ttu-id="1b9e9-111">En general, se debería tener cuidado al modificar el contenido del archivo SMSvcHost.exe.config, porque cualquier configuración especificada en este archivo afecta a todos los servicios de un equipo que utiliza el servicio de uso compartido de puertos de Net.TCP.</span><span class="sxs-lookup"><span data-stu-id="1b9e9-111">In general, care should be taken when modifying the contents of the SMSvcHost.exe.config file, because any configuration settings specified in this file affect all of the services on a computer that uses the Net.TCP Port Sharing Service.</span></span> <span data-ttu-id="1b9e9-112">Esto incluye las aplicaciones de Windows Vista que usan las características de activación de TCP del servicio was (Windows Process Activation Service).</span><span class="sxs-lookup"><span data-stu-id="1b9e9-112">This includes applications on Windows Vista that use the TCP Activation features of the Windows Process Activation Service (WAS).</span></span>  
  
 <span data-ttu-id="1b9e9-113">Sin embargo, a veces puede necesitar cambiar la configuración predeterminada del servicio de uso compartido de puertos de Net.TCP.</span><span class="sxs-lookup"><span data-stu-id="1b9e9-113">However, sometimes you may need to change the default configuration for the Net.TCP Port Sharing Service.</span></span> <span data-ttu-id="1b9e9-114">Por ejemplo, el valor predeterminado de `maxPendingAccepts` es 4 \* número de procesadores.</span><span class="sxs-lookup"><span data-stu-id="1b9e9-114">For example, the default value for `maxPendingAccepts` is 4 \* number of processors.</span></span> <span data-ttu-id="1b9e9-115">Los servidores que hospedan un gran número de servicios que usan el uso compartido de puertos pueden aumentar este valor para lograr un rendimiento máximo.</span><span class="sxs-lookup"><span data-stu-id="1b9e9-115">Servers that host a large number of services that use port sharing may increase this value to achieve maximum throughput.</span></span> <span data-ttu-id="1b9e9-116">El valor predeterminado para `maxPendingConnections` es 100.</span><span class="sxs-lookup"><span data-stu-id="1b9e9-116">The default value for `maxPendingConnections` is 100.</span></span> <span data-ttu-id="1b9e9-117">Considere aumentar este valor también si hay clientes varios simultáneos que llaman al servicio y el servicio está quitando conexiones de cliente.</span><span class="sxs-lookup"><span data-stu-id="1b9e9-117">You should consider increasing this value also if there are multiple concurrent clients calling the service and the service is dropping client connections.</span></span>  
  
 <span data-ttu-id="1b9e9-118">SMSvcHost.exe.config también contiene información sobre las identidades de proceso que pueden utilizar el servicio de uso compartido de puertos.</span><span class="sxs-lookup"><span data-stu-id="1b9e9-118">SMSvcHost.exe.config also contains information about the process identities that may make use of the port sharing service.</span></span> <span data-ttu-id="1b9e9-119">Cuando un proceso se conecta al servicio de uso compartido de puertos para utilizar un puerto TCP compartido, la identidad del proceso de conexión se compara frente a una lista de identidades a las que se permite el uso del servicio de uso compartido de puertos.</span><span class="sxs-lookup"><span data-stu-id="1b9e9-119">When a process connects to the port sharing service to make use of a shared TCP port, the process identity of the connecting process is checked against a list of identities that are permitted to make use of the port sharing service.</span></span> <span data-ttu-id="1b9e9-120">Estas identidades se especifican como identificadores de seguridad (SID) en la sección \<allowAccounts > del archivo SMSvcHost. exe. config.</span><span class="sxs-lookup"><span data-stu-id="1b9e9-120">These identities are specified as security identifiers (SIDs) in the \<allowAccounts> section of the SMSvcHost.exe.config file.</span></span> <span data-ttu-id="1b9e9-121">De forma predeterminada, el permiso de uso del servicio de uso compartido de puertos se concede a las cuentas del sistema (LocalService, LocalSystem y NetworkService) así como a los miembros del grupo Administradores.</span><span class="sxs-lookup"><span data-stu-id="1b9e9-121">By default, permission to use the port sharing service is granted to system accounts (LocalService, LocalSystem, and NetworkService) as well as members of the Administrators group.</span></span> <span data-ttu-id="1b9e9-122">Las aplicaciones que permiten a un proceso se ejecuta como otra identidad (por ejemplo, una identidad de usuario) que se conecten al servicio de uso compartido de puertos deben agregar explícitamente el SID adecuado a SMSvcHost.exe.config (estos cambios no se aplican hasta que se reinicie el proceso de SMSvc.exe).</span><span class="sxs-lookup"><span data-stu-id="1b9e9-122">Applications that allow a process running as another identity (for example, a user identity) to connect to the port sharing service must explicitly add the appropriate SID to the SMSvcHost.exe.config (these changes are not applied until the SMSvc.exe process is restarted).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1b9e9-123">En los sistemas Windows Vista con el control de cuentas de usuario (UAC) habilitado, los usuarios locales requieren permisos elevados, incluso si su cuenta es miembro del grupo administradores.</span><span class="sxs-lookup"><span data-stu-id="1b9e9-123">On Windows Vista systems with User Account Control (UAC) enabled, local users require elevated permissions even if their account is a member of the Administrators group.</span></span> <span data-ttu-id="1b9e9-124">Para permitir que estos usuarios utilicen el servicio de uso compartido de puertos sin elevación, el SID del usuario (o el SID de un grupo del que el usuario es miembro) debe agregarse explícitamente a la sección \<allowAccounts > de SMSvcHost. exe. config.</span><span class="sxs-lookup"><span data-stu-id="1b9e9-124">To allow these users to make use of the port sharing service without elevation, the user's SID (or the SID of a group in which the user is a member) must be explicitly added to the \<allowAccounts> section of SMSvcHost.exe.config.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="1b9e9-125">El archivo SMSvcHost.exe.config predeterminado especifica un valor `etwProviderId` personalizado para evitar que el seguimiento de SMSvcHost.exe interfiera con los seguimientos del servicio.</span><span class="sxs-lookup"><span data-stu-id="1b9e9-125">The default SMSvcHost.exe.config file specifies a custom `etwProviderId` to prevent SMSvcHost.exe tracing from interfering with service traces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b9e9-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b9e9-126">See also</span></span>

- [<span data-ttu-id="1b9e9-127">\<net.tcp></span><span class="sxs-lookup"><span data-stu-id="1b9e9-127">\<net.tcp></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/net-tcp.md)
