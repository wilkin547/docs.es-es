---
title: Utilización de las herramientas de desarrollo de WCF
ms.date: 03/30/2017
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
ms.openlocfilehash: 82bb7e225492bcdba4d2e611de405a09571355c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183079"
---
# <a name="using-the-wcf-development-tools"></a><span data-ttu-id="9fbb9-102">Utilización de las herramientas de desarrollo de WCF</span><span class="sxs-lookup"><span data-stu-id="9fbb9-102">Using the WCF Development Tools</span></span>
<span data-ttu-id="9fbb9-103">En esta sección se describen las herramientas de desarrollo de Visual Studio que pueden ayudarle a desarrollar el WCFservice.</span><span class="sxs-lookup"><span data-stu-id="9fbb9-103">This section describes the Visual Studio development tools that can assist you in developing your WCFservice.</span></span>  
  
 <span data-ttu-id="9fbb9-104">Puede usar las plantillas de Visual Studio como base para crear rápidamente su propio servicio y, a continuación, usar WCF Service Auto Host y WCF Test Client para depurar y probar el servicio.</span><span class="sxs-lookup"><span data-stu-id="9fbb9-104">You can use the Visual Studio templates as a foundation to quickly build your own service, then use WCF Service Auto Host and WCF Test Client to debug and test your service.</span></span> <span data-ttu-id="9fbb9-105">Todas estas herramientas proporcionan una depuración y un ciclo de prueba rápido y estable, y descartan la necesidad de confirmar un modelo de hospedaje en una fase temprana.</span><span class="sxs-lookup"><span data-stu-id="9fbb9-105">These tools together provide a fast and seamless debug and testing cycle, and preclude the need to commit to a hosting model at an early stage.</span></span>  

 > [!NOTE]
 > <span data-ttu-id="9fbb9-106">A partir de Visual Studio 2017, las herramientas de desarrollo de WCF no se instalan de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9fbb9-106">Starting with Visual Studio 2017, the WCF development tools are not installed by default.</span></span> <span data-ttu-id="9fbb9-107">Para usar estas características, debe asegurarse de que el componente de Windows Communication Foundation está seleccionado en el instalador de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9fbb9-107">In order to use these features, you must ensure the Windows Communication Foundation component is selected in the Visual Studio installer.</span></span>
  
## <a name="the-wcf-developer-tools"></a><span data-ttu-id="9fbb9-108">Herramientas de desarrollador de WCF</span><span class="sxs-lookup"><span data-stu-id="9fbb9-108">The WCF Developer Tools</span></span>  
 [<span data-ttu-id="9fbb9-109">Plantillas de Visual Studio para WCF</span><span class="sxs-lookup"><span data-stu-id="9fbb9-109">WCF Visual Studio Templates</span></span>](wcf-vs-templates.md)  
  
 <span data-ttu-id="9fbb9-110">Puede usar las plantillas de proyecto y elemento de Visual Studio predefinidas en Visual Studio para compilar rápidamente servicios WCF y aplicaciones circundantes.</span><span class="sxs-lookup"><span data-stu-id="9fbb9-110">You can use the predefined Visual Studio project and item templates in Visual Studio to quickly build WCF services and surrounding applications.</span></span>  
  
 [<span data-ttu-id="9fbb9-111">Host de servicio WCF (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="9fbb9-111">WCF Service Host (WcfSvcHost.exe)</span></span>](wcf-service-host-wcfsvchost-exe.md)  
  
 <span data-ttu-id="9fbb9-112">El host automático del servicio WCF (WcfSvcHost.exe) le permite iniciar el depurador de Visual Studio (F5) para hospedar y probar automáticamente un servicio que ha implementado.</span><span class="sxs-lookup"><span data-stu-id="9fbb9-112">The WCF Service Auto Host (WcfSvcHost.exe) allows you to launch the Visual Studio debugger (F5) to automatically host and test a service you have implemented.</span></span> <span data-ttu-id="9fbb9-113">A continuación, puede probar el servicio mediante el cliente de prueba WCF (wcfTestClient.exe) o su propio cliente para buscar y corregir los posibles errores.</span><span class="sxs-lookup"><span data-stu-id="9fbb9-113">You can then test the service using the WCF Test Client (wcfTestClient.exe) or your own client to find and fix any potential errors.</span></span>  
  
 [<span data-ttu-id="9fbb9-114">Cliente de prueba de WCF (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="9fbb9-114">WCF Test Client (WcfTestClient.exe)</span></span>](wcf-test-client-wcftestclient-exe.md)  
  
 <span data-ttu-id="9fbb9-115">Cliente de prueba WCF (WcfTestClient.exe) es una herramienta de interfaz gráfica de usuario que le permite introducir parámetros de tipos arbitrarios, enviar esa entrada al servicio y ver la respuesta que el servicio devuelve.</span><span class="sxs-lookup"><span data-stu-id="9fbb9-115">WCF Test Client (WcfTestClient.exe) is a GUI tool that allows you to input parameters of arbitrary types, submit that input to the service, and view the response the service sends back.</span></span> <span data-ttu-id="9fbb9-116">Proporciona una experiencia de prueba de servicio sin problemas cuando se combina con wcf Service Auto Host.</span><span class="sxs-lookup"><span data-stu-id="9fbb9-116">It provides a seamless service testing experience when combined with WCF Service Auto Host.</span></span>  
  
 [<span data-ttu-id="9fbb9-117">Generación de clases de tipos de datos a partir de XML</span><span class="sxs-lookup"><span data-stu-id="9fbb9-117">Generating Data Type Classes from XML</span></span>](generating-data-type-classes-from-xml.md)  
  
 <span data-ttu-id="9fbb9-118">Los datos XML almacenados en el portapapeles se pueden pegar en una página de códigos.</span><span class="sxs-lookup"><span data-stu-id="9fbb9-118">XML data stored in the clipboard can be pasted into a code page.</span></span> <span data-ttu-id="9fbb9-119">Las clases definidas en los datos se convertirán en tipos de código.</span><span class="sxs-lookup"><span data-stu-id="9fbb9-119">The classes defined in the data will be converted to code types.</span></span>  
  
## <a name="using-the-tools-without-administrator-privilege"></a><span data-ttu-id="9fbb9-120">Utilización de las herramientas sin el privilegio de administrador</span><span class="sxs-lookup"><span data-stu-id="9fbb9-120">Using the Tools without Administrator privilege</span></span>  
 <span data-ttu-id="9fbb9-121">Para permitir que los usuarios sin privilegios de administrador desarrollenhttp://+:8731/Design_Time_Addressesservicios WCF, se crea una ACL (Lista de control de acceso) para el espacio de nombres " " durante la instalación de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="9fbb9-121">To enable users without administrator privilege to develop WCF services, an ACL (Access Control List) is created for the namespace "http://+:8731/Design_Time_Addresses" during the installation of Visual Studio.</span></span> <span data-ttu-id="9fbb9-122">La ACL se establece en la interfaz de usuario (UI), en la que se incluyen todos los usuarios interactivos que iniciaron sesión en el equipo.</span><span class="sxs-lookup"><span data-stu-id="9fbb9-122">The ACL is set to (UI), which includes all interactive users logged on to the machine.</span></span> <span data-ttu-id="9fbb9-123">Los administradores pueden agregar o quitar usuarios de esta ACL o abrir puertos adicionales. Esta ACL permite que las plantillas WCF o WF envíen y reciban datos con su configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9fbb9-123">Administrators can add or remove users from this ACL, or open additional ports.This ACL enables WCF or WF templates to send and receive data in their default configuration.</span></span> <span data-ttu-id="9fbb9-124">También permite a los usuarios usar el host automático del servicio WCF (wcfSvcHost.exe) sin concederles privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="9fbb9-124">It also enables users to use the WCF Service Auto Host (wcfSvcHost.exe) without granting them administrator privileges.</span></span>  
  
 <span data-ttu-id="9fbb9-125">Puede modificar el acceso mediante la herramienta Netsh.exe en Windows Vista en la cuenta de administrador con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="9fbb9-125">You can modify access using the Netsh.exe tool in Windows Vista under the elevated administrator account.</span></span> <span data-ttu-id="9fbb9-126">En el siguiente ejemplo se muestra el uso de Netsh.exe.</span><span class="sxs-lookup"><span data-stu-id="9fbb9-126">The following is an example of using Netsh.exe.</span></span>  
  
```console  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 <span data-ttu-id="9fbb9-127">Para obtener más información acerca de Netsh.exe, vea [Cómo utilizar la herramienta Netsh.exe y](https://docs.microsoft.com/previous-versions/tn-archive/bb490939(v=technet.10))los modificadores de línea de comandos .</span><span class="sxs-lookup"><span data-stu-id="9fbb9-127">For more information about Netsh.exe, see [How to Use the Netsh.exe Tool and Command-Line Switches](https://docs.microsoft.com/previous-versions/tn-archive/bb490939(v=technet.10)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fbb9-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9fbb9-128">See also</span></span>

- [<span data-ttu-id="9fbb9-129">Plantillas de Visual Studio para WCF</span><span class="sxs-lookup"><span data-stu-id="9fbb9-129">WCF Visual Studio Templates</span></span>](wcf-vs-templates.md)
- [<span data-ttu-id="9fbb9-130">Host de servicio WCF (WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="9fbb9-130">WCF Service Host (WcfSvcHost.exe)</span></span>](wcf-service-host-wcfsvchost-exe.md)
- [<span data-ttu-id="9fbb9-131">Cliente de prueba de WCF (WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="9fbb9-131">WCF Test Client (WcfTestClient.exe)</span></span>](wcf-test-client-wcftestclient-exe.md)
