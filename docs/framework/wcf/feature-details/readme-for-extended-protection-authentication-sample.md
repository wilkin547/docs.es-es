---
title: "Archivo ReadMe del ejemplo de protección extendida para la autenticación"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 80bf2e97-398d-4db5-9040-d96478a2ccab
caps.latest.revision: "3"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 3981a0d0c82b8bc35536a9afd702e753fcf07db5
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="readme-for-extended-protection-authentication-sample"></a><span data-ttu-id="7572e-102">Archivo ReadMe del ejemplo de protección extendida para la autenticación</span><span class="sxs-lookup"><span data-stu-id="7572e-102">ReadMe for Extended Protection Authentication Sample</span></span>
<span data-ttu-id="7572e-103">Protección extendida es una iniciativa de seguridad para protegerse contra ataques de tipo man in the middle (MITM), en el que un atacante (el "man-in-the-middle") intercepta las credenciales del cliente y las usa para tener acceso a recursos seguros en el servidor del cliente previsto.</span><span class="sxs-lookup"><span data-stu-id="7572e-103">Extended Protection is a security initiative to protect against man-in-the-middle (MITM) attacks, in which an attacker (the "man-in-the-middle") intercepts a client’s credentials and uses them to access secure resources on the client’s intended server.</span></span>  
  
 <span data-ttu-id="7572e-104">Para obtener más información, consulte [protección ampliada para la introducción a la autenticación](../../../../docs/framework/wcf/feature-details/extended-protection-for-authentication-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7572e-104">For more information, see [Extended Protection for Authentication Overview](../../../../docs/framework/wcf/feature-details/extended-protection-for-authentication-overview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7572e-105">Esta muestra solo funciona cuando se hospeda en IIS.</span><span class="sxs-lookup"><span data-stu-id="7572e-105">This sample only works when hosted on IIS.</span></span> <span data-ttu-id="7572e-106">No funciona en el servidor de desarrollo de Visual Studio, ya que este no admite HTTPS.</span><span class="sxs-lookup"><span data-stu-id="7572e-106">It does not work on Visual Studio Development Server because that does not support HTTPS.</span></span>  
  
## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="7572e-107">Para configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="7572e-107">To Set Up, Build, and Run the Sample</span></span>  
  
1.  <span data-ttu-id="7572e-108">Instale IIS en el equipo mediante Agregar o quitar programas -> Características de Windows.</span><span class="sxs-lookup"><span data-stu-id="7572e-108">Install IIS on the machine from Add/Remove Programs -> Windows Features.</span></span>  
  
2.  <span data-ttu-id="7572e-109">Active la autenticación de Windows en las características de Windows: Internet Information Services -> Servicios World Wide Web -> Seguridad -> Autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="7572e-109">Turn on Windows Authentication in Windows features: Internet Information Services -> World Wide Web Services -> Security -> Windows Authentication.</span></span>  
  
3.  <span data-ttu-id="7572e-110">Active la activación HTTP en las características de Windows: Microsoft .NET Framework 3.5.1 -> Activación HTTP de Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="7572e-110">Turn on HTTP Activation in Windows features: Microsoft .NET Framework 3.5.1 -> Windows Communication Foundation HTTP Activation.</span></span>  
  
4.  <span data-ttu-id="7572e-111">Este ejemplo requiere que el cliente establezca un canal seguro con el servidor, por lo que es necesaria la presencia de un certificado de servidor que se puede instalar desde el Administrador de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="7572e-111">This sample requires the client to establish a secure channel with the server and so it requires the presence of a server certificate which can be installed from Internet Information Services (IIS) Manager.</span></span>  
  
    1.  <span data-ttu-id="7572e-112">Abra el Administrador de IIS -> Certificados de servidor (en la pestaña de vista de características).</span><span class="sxs-lookup"><span data-stu-id="7572e-112">Open the IIS manager -> Server certificates (from the feature view tab).</span></span>  
  
    2.  <span data-ttu-id="7572e-113">Con fines de prueba de esta muestra, puede crear un certificado autofirmado.</span><span class="sxs-lookup"><span data-stu-id="7572e-113">For the purpose of testing this sample, you can create a self-signed certificate.</span></span> <span data-ttu-id="7572e-114">(Si no desea que Internet Explorer le indique que el certificado no es seguro, puede instalarlo en el almacén Entidades emisoras de certificados raíz de confianza).</span><span class="sxs-lookup"><span data-stu-id="7572e-114">(If you don’t want Internet Explorer to prompt you about the certificate not being secure, you can install it in the Trusted Certificate Root authority store).</span></span>  
  
5.  <span data-ttu-id="7572e-115">Vaya al panel Acciones del sitio web predeterminado.</span><span class="sxs-lookup"><span data-stu-id="7572e-115">Go to the Actions pane for the Default Web site.</span></span> <span data-ttu-id="7572e-116">Haga clic en Modificar sitio -> Enlaces.</span><span class="sxs-lookup"><span data-stu-id="7572e-116">Click Edit Site -> Bindings.</span></span> <span data-ttu-id="7572e-117">Agregue HTTPS como tipo si aún no está presente, con el número de puerto 443, y asigne el certificado SSL creado en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="7572e-117">Add HTTPS as a type if it is not already present, with port number 443, and assign the SSL certificate created in the above step.</span></span>  
  
6.  <span data-ttu-id="7572e-118">Compile el servicio.</span><span class="sxs-lookup"><span data-stu-id="7572e-118">Build the service.</span></span> <span data-ttu-id="7572e-119">Esto crea un directorio virtual en IIS (a partir de la acción posterior a la compilación especificada en las propiedades del proyecto) y copia los archivos dll, .svc y config según sea necesario para que un servicio se hospede en web.</span><span class="sxs-lookup"><span data-stu-id="7572e-119">This creates a virtual directory in IIS for you (from the post build action specified in the project properties) and copies the dll, .svc and config files as needed for a service to be Web hosted.</span></span>  
  
7.  <span data-ttu-id="7572e-120">Abra el Administrador de IIS.</span><span class="sxs-lookup"><span data-stu-id="7572e-120">Open the IIS Manager.</span></span> <span data-ttu-id="7572e-121">Haga clic con el botón secundario en el directorio virtual (ExtendedProtection) que creó en el paso anterior y seleccione Convertir en aplicación.</span><span class="sxs-lookup"><span data-stu-id="7572e-121">Right-click the virtual directory (ExtendedProtection) that you created in the previous step and select Convert to Application.</span></span>  
  
8.  <span data-ttu-id="7572e-122">Abra el módulo de autenticación en el Administrador de IIS para este directorio virtual y habilite la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="7572e-122">Open the Authentication module in IIS Manager for this virtual directory and enable Windows Authentication.</span></span>  
  
9. <span data-ttu-id="7572e-123">Abra la Configuración avanzada de la autenticación de Windows para este directorio virtual y establézcala en Requerida, ya que en el ejemplo el valor ExtendedProtection correspondiente está establecido en Siempre.</span><span class="sxs-lookup"><span data-stu-id="7572e-123">Open the Advanced Settings for Windows Authentication for this virtual directory and set it to Required, since, in the sample, the corresponding ExtendedProtection setting is set to Always.</span></span>  
  
10. <span data-ttu-id="7572e-124">Puede probar el servicio obteniendo acceso a la dirección URL desde una ventana del explorador.</span><span class="sxs-lookup"><span data-stu-id="7572e-124">You can test the service by accessing the URL from a browser window.</span></span> <span data-ttu-id="7572e-125">Si desea tener acceso a esta dirección URL desde varios equipos, asegúrese de que el firewall está abierto para todas las conexiones HTTP y HTTPS entrantes.</span><span class="sxs-lookup"><span data-stu-id="7572e-125">If you want to access this URL from a cross machine, make sure that the firewall is opened for all incoming HTTP and HTTPS connections.</span></span>  
  
11. <span data-ttu-id="7572e-126">Abra el archivo de configuración de cliente y proporcione un nombre completo de equipo para el \<cliente >- \<endpoint >-address attribute, reemplace << full_machine_name >>.</span><span class="sxs-lookup"><span data-stu-id="7572e-126">Open the client config file and provide a full machine name for the \<client> - \<endpoint> - address attribute, replacing <<full_machine_name>>.</span></span>  
  
12. <span data-ttu-id="7572e-127">Ejecute el cliente.</span><span class="sxs-lookup"><span data-stu-id="7572e-127">Run the client.</span></span> <span data-ttu-id="7572e-128">El cliente se comunica con el servicio estableciendo un canal seguro y usando la protección extendida.</span><span class="sxs-lookup"><span data-stu-id="7572e-128">The client communicates to the service by establishing a secure channel and using extended protection under the covers.</span></span>
