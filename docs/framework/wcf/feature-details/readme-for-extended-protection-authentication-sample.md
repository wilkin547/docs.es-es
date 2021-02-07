---
description: Más información sobre el archivo Léame para el ejemplo de autenticación de protección ampliada
title: Archivo ReadMe del ejemplo de protección extendida para la autenticación
ms.date: 03/30/2017
ms.assetid: 80bf2e97-398d-4db5-9040-d96478a2ccab
ms.openlocfilehash: edab04c7762bf8964f634107debd3de35a7702ab
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99733312"
---
# <a name="readme-for-extended-protection-authentication-sample"></a><span data-ttu-id="d27eb-103">Archivo ReadMe del ejemplo de protección extendida para la autenticación</span><span class="sxs-lookup"><span data-stu-id="d27eb-103">ReadMe for Extended Protection Authentication Sample</span></span>

<span data-ttu-id="d27eb-104">La protección ampliada es una iniciativa de seguridad para protegerse contra ataques de tipo "Man in the Middle" (MITM), en los que un atacante ("Man in the Middle") intercepta las credenciales de un cliente y las utiliza para obtener acceso a recursos seguros en el servidor previsto del cliente.</span><span class="sxs-lookup"><span data-stu-id="d27eb-104">Extended Protection is a security initiative to protect against man-in-the-middle (MITM) attacks, in which an attacker (the "man-in-the-middle") intercepts a client’s credentials and uses them to access secure resources on the client’s intended server.</span></span>

<span data-ttu-id="d27eb-105">Para obtener más información, vea [información general sobre protección ampliada para la autenticación](extended-protection-for-authentication-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d27eb-105">For more information, see [Extended Protection for Authentication Overview](extended-protection-for-authentication-overview.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d27eb-106">Esta muestra solo funciona cuando se hospeda en IIS.</span><span class="sxs-lookup"><span data-stu-id="d27eb-106">This sample only works when hosted on IIS.</span></span> <span data-ttu-id="d27eb-107">No funciona en el servidor de desarrollo de Visual Studio, ya que este no admite HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d27eb-107">It does not work on Visual Studio Development Server because that does not support HTTPS.</span></span>

## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="d27eb-108">Para configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="d27eb-108">To Set Up, Build, and Run the Sample</span></span>

1. <span data-ttu-id="d27eb-109">Instale IIS en el equipo desde agregar o quitar programas-> características de Windows.</span><span class="sxs-lookup"><span data-stu-id="d27eb-109">Install IIS on the machine from Add/Remove Programs -> Windows Features.</span></span>

2. <span data-ttu-id="d27eb-110">Active la autenticación de Windows en características de Windows: Internet Information Services > World Wide Web Services-> Security-> autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="d27eb-110">Turn on Windows Authentication in Windows features: Internet Information Services -> World Wide Web Services -> Security -> Windows Authentication.</span></span>

3. <span data-ttu-id="d27eb-111">Active la activación HTTP en las características de Windows: Microsoft .NET Framework 3.5.1-> Windows Communication Foundation la activación HTTP.</span><span class="sxs-lookup"><span data-stu-id="d27eb-111">Turn on HTTP Activation in Windows features: Microsoft .NET Framework 3.5.1 -> Windows Communication Foundation HTTP Activation.</span></span>

4. <span data-ttu-id="d27eb-112">Este ejemplo requiere que el cliente establezca un canal seguro con el servidor, por lo que es necesaria la presencia de un certificado de servidor que se puede instalar desde el Administrador de Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="d27eb-112">This sample requires the client to establish a secure channel with the server and so it requires the presence of a server certificate which can be installed from Internet Information Services (IIS) Manager.</span></span>

    1. <span data-ttu-id="d27eb-113">Abra el administrador de IIS: certificados de servidor de > (en la pestaña vista de características).</span><span class="sxs-lookup"><span data-stu-id="d27eb-113">Open the IIS manager -> Server certificates (from the feature view tab).</span></span>

    2. <span data-ttu-id="d27eb-114">Con fines de prueba de esta muestra, puede crear un certificado autofirmado.</span><span class="sxs-lookup"><span data-stu-id="d27eb-114">For the purpose of testing this sample, you can create a self-signed certificate.</span></span> <span data-ttu-id="d27eb-115">(Si no desea que Internet Explorer le indique que el certificado no es seguro, puede instalarlo en el almacén Entidades emisoras de certificados raíz de confianza).</span><span class="sxs-lookup"><span data-stu-id="d27eb-115">(If you don’t want Internet Explorer to prompt you about the certificate not being secure, you can install it in the Trusted Certificate Root authority store).</span></span>

5. <span data-ttu-id="d27eb-116">Vaya al panel Acciones del sitio web predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d27eb-116">Go to the Actions pane for the Default Web site.</span></span> <span data-ttu-id="d27eb-117">Haga clic en Editar > enlaces del sitio.</span><span class="sxs-lookup"><span data-stu-id="d27eb-117">Click Edit Site -> Bindings.</span></span> <span data-ttu-id="d27eb-118">Agregue HTTPS como tipo si aún no está presente, con el número de puerto 443, y asigne el certificado SSL creado en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="d27eb-118">Add HTTPS as a type if it is not already present, with port number 443, and assign the SSL certificate created in the above step.</span></span>

6. <span data-ttu-id="d27eb-119">Compile el servicio.</span><span class="sxs-lookup"><span data-stu-id="d27eb-119">Build the service.</span></span> <span data-ttu-id="d27eb-120">Esto crea un directorio virtual en IIS (a partir de la acción posterior a la compilación especificada en las propiedades del proyecto) y copia los archivos dll, .svc y config según sea necesario para que un servicio se hospede en web.</span><span class="sxs-lookup"><span data-stu-id="d27eb-120">This creates a virtual directory in IIS for you (from the post build action specified in the project properties) and copies the dll, .svc and config files as needed for a service to be Web hosted.</span></span>

7. <span data-ttu-id="d27eb-121">Abra el Administrador de IIS.</span><span class="sxs-lookup"><span data-stu-id="d27eb-121">Open the IIS Manager.</span></span> <span data-ttu-id="d27eb-122">Haga clic con el botón secundario en el directorio virtual (ExtendedProtection) que creó en el paso anterior y seleccione Convertir en aplicación.</span><span class="sxs-lookup"><span data-stu-id="d27eb-122">Right-click the virtual directory (ExtendedProtection) that you created in the previous step and select Convert to Application.</span></span>

8. <span data-ttu-id="d27eb-123">Abra el módulo de autenticación en el Administrador de IIS para este directorio virtual y habilite la autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="d27eb-123">Open the Authentication module in IIS Manager for this virtual directory and enable Windows Authentication.</span></span>

9. <span data-ttu-id="d27eb-124">Abra la Configuración avanzada de la autenticación de Windows para este directorio virtual y establézcala en Requerida, ya que en el ejemplo el valor ExtendedProtection correspondiente está establecido en Siempre.</span><span class="sxs-lookup"><span data-stu-id="d27eb-124">Open the Advanced Settings for Windows Authentication for this virtual directory and set it to Required, since, in the sample, the corresponding ExtendedProtection setting is set to Always.</span></span>

10. <span data-ttu-id="d27eb-125">Puede probar el servicio obteniendo acceso a la dirección URL desde una ventana del explorador.</span><span class="sxs-lookup"><span data-stu-id="d27eb-125">You can test the service by accessing the URL from a browser window.</span></span> <span data-ttu-id="d27eb-126">Si desea tener acceso a esta dirección URL desde varios equipos, asegúrese de que el firewall está abierto para todas las conexiones HTTP y HTTPS entrantes.</span><span class="sxs-lookup"><span data-stu-id="d27eb-126">If you want to access this URL from a cross machine, make sure that the firewall is opened for all incoming HTTP and HTTPS connections.</span></span>

11. <span data-ttu-id="d27eb-127">Abra el archivo de configuración del cliente y proporcione un nombre de equipo completo para el \<client>  -  \<endpoint> atributo-address y reemplace \<full_machine_name> .</span><span class="sxs-lookup"><span data-stu-id="d27eb-127">Open the client config file and provide a full machine name for the \<client> - \<endpoint> - address attribute, replacing \<full_machine_name>.</span></span>

12. <span data-ttu-id="d27eb-128">Ejecute el cliente.</span><span class="sxs-lookup"><span data-stu-id="d27eb-128">Run the client.</span></span> <span data-ttu-id="d27eb-129">El cliente se comunica con el servicio estableciendo un canal seguro y usando la protección extendida.</span><span class="sxs-lookup"><span data-stu-id="d27eb-129">The client communicates to the service by establishing a secure channel and using extended protection under the covers.</span></span>
