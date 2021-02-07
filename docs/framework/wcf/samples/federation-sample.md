---
description: 'Más información acerca de: ejemplo de Federación'
title: Ejemplo de federación
ms.date: 03/30/2017
ms.assetid: 7e9da0ca-e925-4644-aa96-8bfaf649d4bb
ms.openlocfilehash: a85a290988b6cbb4b30a1098f3558ec34ead1d50
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99704087"
---
# <a name="federation-sample"></a><span data-ttu-id="e24a4-103">Ejemplo de federación</span><span class="sxs-lookup"><span data-stu-id="e24a4-103">Federation Sample</span></span>

<span data-ttu-id="e24a4-104">Este ejemplo muestra la seguridad aliada.</span><span class="sxs-lookup"><span data-stu-id="e24a4-104">This sample demonstrates federated security.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="e24a4-105">Detalles del ejemplo</span><span class="sxs-lookup"><span data-stu-id="e24a4-105">Sample Details</span></span>  

 <span data-ttu-id="e24a4-106">Windows Communication Foundation (WCF) proporciona compatibilidad para la implementación de arquitecturas de seguridad federadas a través de `wsFederationHttpBinding` .</span><span class="sxs-lookup"><span data-stu-id="e24a4-106">Windows Communication Foundation (WCF) provides support for deploying federated security architectures through the `wsFederationHttpBinding`.</span></span> <span data-ttu-id="e24a4-107">El `wsFederationHttpBinding` proporciona un enlace seguro, confiable e interoperable que implica el uso de HTTP como mecanismo de transporte subyacente para la comunicación de solicitud-respuesta, y Text/XML, como el formato de conexión para la codificación.</span><span class="sxs-lookup"><span data-stu-id="e24a4-107">The `wsFederationHttpBinding` provides a secure, reliable, and interoperable binding that involves the use of HTTP as the underlying transport mechanism for request/reply communication, and Text/XML as the wire format for encoding.</span></span> <span data-ttu-id="e24a4-108">Para obtener más información acerca de la Federación en WCF, consulte [Federación](../feature-details/federation.md).</span><span class="sxs-lookup"><span data-stu-id="e24a4-108">For more information about Federation in WCF, see [Federation](../feature-details/federation.md).</span></span>  
  
 <span data-ttu-id="e24a4-109">El escenario se compone de 4 partes:</span><span class="sxs-lookup"><span data-stu-id="e24a4-109">The scenario is made up of 4 pieces:</span></span>  
  
- <span data-ttu-id="e24a4-110">Servicio de la librería</span><span class="sxs-lookup"><span data-stu-id="e24a4-110">BookStore service</span></span>  
  
- <span data-ttu-id="e24a4-111">STS BookStore</span><span class="sxs-lookup"><span data-stu-id="e24a4-111">BookStore STS</span></span>  
  
- <span data-ttu-id="e24a4-112">STS HomeRealm </span><span class="sxs-lookup"><span data-stu-id="e24a4-112">HomeRealm STS</span></span>  
  
- <span data-ttu-id="e24a4-113">Cliente de librería</span><span class="sxs-lookup"><span data-stu-id="e24a4-113">BookStore Client</span></span>  
  
 <span data-ttu-id="e24a4-114">El servicio de librería admite dos operaciones, `BrowseBooks` y `BuyBook`.</span><span class="sxs-lookup"><span data-stu-id="e24a4-114">The BookStore service supports two operations, `BrowseBooks` and `BuyBook`.</span></span> <span data-ttu-id="e24a4-115">Permite el acceso anónimo a la operación `BrowseBooks`, pero requiere acceso autenticado para tener acceso a la operación `BuyBooks`.</span><span class="sxs-lookup"><span data-stu-id="e24a4-115">It allows anonymous access to the `BrowseBooks` operation, but requires authenticated access to access the `BuyBooks` operation.</span></span> <span data-ttu-id="e24a4-116">La autenticación toma el formulario de un token emitido por el STS BookStore.</span><span class="sxs-lookup"><span data-stu-id="e24a4-116">The authentication takes the form of a token issued by the BookStore STS.</span></span> <span data-ttu-id="e24a4-117">El archivo de configuración para el Servicio de librería dirige los clientes a la STS BookStore mediante `wsFederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="e24a4-117">The configuration file for the BookStore Service points clients to the BookStore STS using the `wsFederationHttpBinding`.</span></span>  
  
```xml  
<wsFederationHttpBinding>  
<!-- This is the Service binding for the BuyBooks endpoint. It redirects clients to the BookStore STS -->  
    <binding name='BuyBookBinding'>  
        <security mode="Message">  
            <message>  
                <issuerMetadata  
  address='http://localhost/FederationSample/BookStoreSTS/STS.svc/mex' >  
                    <identity>  
                        <dns value ='BookStoreSTS.com'/>  
                    </identity>  
                </issuerMetadata>  
            </message>  
        </security>  
    </binding>  
</wsFederationHttpBinding>  
```  
  
 <span data-ttu-id="e24a4-118">STS BookStore requiere a continuación que los clientes se autentiquen mediante un token emitido por el STS HomeRealm.</span><span class="sxs-lookup"><span data-stu-id="e24a4-118">The BookStore STS then requires that clients authenticate using a token issued by the HomeRealm STS.</span></span> <span data-ttu-id="e24a4-119">De nuevo, el archivo de configuración para el STS BookStore dirige los clientes al STS HomeRealm mediante `wsFederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="e24a4-119">Again, the configuration file for the BookStore STS points clients to the HomeRealm STS using the `wsFederationHttpBinding`.</span></span>  
  
```xml  
<wsFederationHttpBinding>  
 <!-- This is the binding for the clients requesting tokens from this STS. It redirects clients to the HomeRealm STS -->  
    <binding name='BookStoreSTSBinding'>  
        <security mode='Message'>  
            <message>  
                <issuerMetadata  
 address='http://localhost/FederationSample/HomeRealmSTS/STS.svc/mex' >  
                    <identity>  
                        <dns value ='HomeRealmSTS.com' />  
                    </identity>  
                </issuerMetadata>  
            </message>  
        </security>  
    </binding>  
</wsFederationHttpBinding>  
```  
  
 <span data-ttu-id="e24a4-120">La secuencia de eventos, al tener acceso a la operación `BuyBook`, es como sigue:</span><span class="sxs-lookup"><span data-stu-id="e24a4-120">The sequence of events when accessing the `BuyBook` operation is as follows:</span></span>  
  
1. <span data-ttu-id="e24a4-121">El cliente autentica el STS HomeRealm mediante las credenciales de Windows.</span><span class="sxs-lookup"><span data-stu-id="e24a4-121">The client authenticates to the HomeRealm STS using Windows credentials.</span></span>  
  
2. <span data-ttu-id="e24a4-122">El STS HomeRealm emite un token que se puede utilizar para autenticar el STS BookStore.</span><span class="sxs-lookup"><span data-stu-id="e24a4-122">The HomeRealm STS issues a token that can be used to authenticate to the BookStore STS.</span></span>  
  
3. <span data-ttu-id="e24a4-123">El cliente autentica el STS BookStore mediante el token emitido por el STS HomeRealm.</span><span class="sxs-lookup"><span data-stu-id="e24a4-123">The client authenticates to the BookStore STS using the token issued by the HomeRealm STS.</span></span>  
  
4. <span data-ttu-id="e24a4-124">El STS BookStore emite un token que se puede utilizar para autenticar el servicio BookStore.</span><span class="sxs-lookup"><span data-stu-id="e24a4-124">The BookStore STS issues a token that can be used to authenticate to the BookStore Service.</span></span>  
  
5. <span data-ttu-id="e24a4-125">El cliente autentica el servicio de BookStore mediante el token emitido por el STS BookStore.</span><span class="sxs-lookup"><span data-stu-id="e24a4-125">The client authenticates to the BookStore service using the token issued by the BookStore STS.</span></span>  
  
6. <span data-ttu-id="e24a4-126">El cliente tiene acceso a la operación `BuyBook`.</span><span class="sxs-lookup"><span data-stu-id="e24a4-126">The client accesses the `BuyBook` operation.</span></span>  
  
 <span data-ttu-id="e24a4-127">Vea las instrucciones siguientes acerca de cómo configurar y ejecutar este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="e24a4-127">See the following instructions about how to set up and run this sample.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e24a4-128">Para ejecutar este ejemplo, debe tener permisos de escritura en el directorio **wwwroot** .</span><span class="sxs-lookup"><span data-stu-id="e24a4-128">You must have Write permissions to the **wwwroot** directory to run this sample.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="e24a4-129">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="e24a4-129">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="e24a4-130">Abra la ventana de comandos de SDK.</span><span class="sxs-lookup"><span data-stu-id="e24a4-130">Open the SDK command window.</span></span> <span data-ttu-id="e24a4-131">En la ruta de acceso del ejemplo, ejecute Setup.bat.</span><span class="sxs-lookup"><span data-stu-id="e24a4-131">In the sample path, run Setup.bat.</span></span> <span data-ttu-id="e24a4-132">Esto crea directorios virtuales requeridos para obtener el ejemplo e instala los certificados necesarios con permisos adecuados.</span><span class="sxs-lookup"><span data-stu-id="e24a4-132">This creates the virtual directories required for the sample and installs the required certificates with appropriate permissions.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="e24a4-133">El archivo por lotes Setup.bat está diseñado para ejecutarse desde el símbolo del sistema de Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="e24a4-133">The Setup.bat batch file is designed to be run from a Windows SDK Command Prompt.</span></span> <span data-ttu-id="e24a4-134">Requiere que la variable de entorno de MSSDK se dirija al directorio donde está instalado el SDK.</span><span class="sxs-lookup"><span data-stu-id="e24a4-134">It requires that the MSSDK environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="e24a4-135">Esta variable de entorno se establece automáticamente dentro de un símbolo del sistema de Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="e24a4-135">This environment variable is automatically set within a Windows SDK Command Prompt.</span></span> <span data-ttu-id="e24a4-136">En Windows Vista, debe asegurarse de que la compatibilidad con la administración de IIS 6,0 está instalada porque la configuración utiliza scripts de administrador de IIS.</span><span class="sxs-lookup"><span data-stu-id="e24a4-136">On Windows Vista, you must ensure that IIS 6.0 Management Compatibility is installed because the set up uses IIS administrator scripts.</span></span> <span data-ttu-id="e24a4-137">La ejecución del script de instalación en Windows Vista requiere privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="e24a4-137">Running the set-up script on Windows Vista requires administrator privileges.</span></span>  
  
2. <span data-ttu-id="e24a4-138">Abra FederationSample. sln en Visual Studio y seleccione **compilar solución** en el menú **compilar** .</span><span class="sxs-lookup"><span data-stu-id="e24a4-138">Open FederationSample.sln in Visual Studio and select **Build Solution** from the **Build** menu.</span></span> <span data-ttu-id="e24a4-139">De esta forma se compilan los archivos de proyecto comunes, servicio Bookstore, STS Bookstore, STS HomeRealm, y los implementa en IIS.</span><span class="sxs-lookup"><span data-stu-id="e24a4-139">This builds the common project files, Bookstore service, Bookstore STS, HomeRealm STS, and deploys them in IIS.</span></span> <span data-ttu-id="e24a4-140">De esta forma también se compila la aplicación cliente Bookstore y coloca el BookStoreClient.exe ejecutable en la carpeta FederationSample\BookStoreClient\bin\Debug.</span><span class="sxs-lookup"><span data-stu-id="e24a4-140">This also builds the Bookstore client application and places the executable BookStoreClient.exe in the FederationSample\BookStoreClient\bin\Debug folder.</span></span>  
  
3. <span data-ttu-id="e24a4-141">Haga doble clic en BookStoreClient.exe.</span><span class="sxs-lookup"><span data-stu-id="e24a4-141">Double-click BookStoreClient.exe.</span></span> <span data-ttu-id="e24a4-142">Se muestra la ventana BookStoreClient.</span><span class="sxs-lookup"><span data-stu-id="e24a4-142">The BookStoreClient window is displayed.</span></span>  
  
4. <span data-ttu-id="e24a4-143">Puede examinar los libros disponibles en la librería haciendo clic en **examinar libros**.</span><span class="sxs-lookup"><span data-stu-id="e24a4-143">You can browse the books available in the bookstore by clicking **Browse Books**.</span></span>  
  
5. <span data-ttu-id="e24a4-144">Para comprar un libro determinado, seleccione el libro en la lista y haga clic en **comprar libro**.</span><span class="sxs-lookup"><span data-stu-id="e24a4-144">To purchase a particular book, select the book in the list and click **Buy Book**.</span></span> <span data-ttu-id="e24a4-145">La aplicación se inicia y autentica mediante la autenticación de Windows con el Servicio de token de seguridad de HomeRealm.</span><span class="sxs-lookup"><span data-stu-id="e24a4-145">The application starts up and authenticates using Windows authentication with the HomeRealm Security Token Service.</span></span>  
  
     <span data-ttu-id="e24a4-146">El ejemplo se configura para permitirles a los usuarios comprar libros que cuesten 15$ o menos.</span><span class="sxs-lookup"><span data-stu-id="e24a4-146">The sample is configured to allow users to purchase books that cost $15 or less.</span></span> <span data-ttu-id="e24a4-147">Intentar comprar libros que cuesten más de 15 $ provoca que el cliente reciba un mensaje de acceso denegado en el servicio de almacén de libros.</span><span class="sxs-lookup"><span data-stu-id="e24a4-147">Attempting to buy books that cost more than $15 results in the client getting an Access Denied message from the Book Store Service.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="e24a4-148">El ejemplo no actualiza el límite de crédito del usuario después de una compra.</span><span class="sxs-lookup"><span data-stu-id="e24a4-148">The sample does not update the user’s credit limit after a purchase.</span></span> <span data-ttu-id="e24a4-149">Puede comprar repetidamente libros dentro del límite de crédito del usuario (fijo).</span><span class="sxs-lookup"><span data-stu-id="e24a4-149">You can repeatedly purchase books within the user’s (fixed) credit limit.</span></span>  
  
#### <a name="to-clean-up"></a><span data-ttu-id="e24a4-150">Para realizar una limpieza</span><span class="sxs-lookup"><span data-stu-id="e24a4-150">To clean up</span></span>  
  
1. <span data-ttu-id="e24a4-151">Ejecute Cleanup.bat.</span><span class="sxs-lookup"><span data-stu-id="e24a4-151">Run Cleanup.bat.</span></span> <span data-ttu-id="e24a4-152">De esta forma se eliminan los directorios virtuales que se crearon durante la instalación y también se quitan los certificados instalados durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="e24a4-152">This deletes the virtual directories that were created during set up and also removes the certificates installed during setup.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="e24a4-153">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="e24a4-153">The samples may already be installed on your machine.</span></span> <span data-ttu-id="e24a4-154">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="e24a4-154">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="e24a4-155">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="e24a4-155">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="e24a4-156">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="e24a4-156">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\Federation`  
