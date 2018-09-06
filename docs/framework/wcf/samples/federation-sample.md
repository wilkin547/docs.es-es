---
title: Ejemplo de federación
ms.date: 03/30/2017
ms.assetid: 7e9da0ca-e925-4644-aa96-8bfaf649d4bb
ms.openlocfilehash: 49a13b292a627c054510a10445e1e64ab869162c
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43744646"
---
# <a name="federation-sample"></a><span data-ttu-id="2ae43-102">Ejemplo de federación</span><span class="sxs-lookup"><span data-stu-id="2ae43-102">Federation Sample</span></span>
<span data-ttu-id="2ae43-103">Este ejemplo muestra la seguridad aliada.</span><span class="sxs-lookup"><span data-stu-id="2ae43-103">This sample demonstrates federated security.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="2ae43-104">Detalles del ejemplo</span><span class="sxs-lookup"><span data-stu-id="2ae43-104">Sample Details</span></span>  
 <span data-ttu-id="2ae43-105">Windows Communication Foundation (WCF) proporciona compatibilidad para la implementación de arquitecturas de seguridad federadas a través de la `wsFederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="2ae43-105">Windows Communication Foundation (WCF) provides support for deploying federated security architectures through the `wsFederationHttpBinding`.</span></span> <span data-ttu-id="2ae43-106">El `wsFederationHttpBinding` proporciona un enlace seguro, confiable e interoperable que implica el uso de HTTP como mecanismo de transporte subyacente para la comunicación de solicitud-respuesta, y Text/XML, como el formato de conexión para la codificación.</span><span class="sxs-lookup"><span data-stu-id="2ae43-106">The `wsFederationHttpBinding` provides a secure, reliable, and interoperable binding that involves the use of HTTP as the underlying transport mechanism for request/reply communication, and Text/XML as the wire format for encoding.</span></span> <span data-ttu-id="2ae43-107">Para obtener más información acerca de la federación en WCF, vea [federación](../../../../docs/framework/wcf/feature-details/federation.md).</span><span class="sxs-lookup"><span data-stu-id="2ae43-107">For more information about Federation in WCF, see [Federation](../../../../docs/framework/wcf/feature-details/federation.md).</span></span>  
  
 <span data-ttu-id="2ae43-108">El escenario se compone de 4 partes:</span><span class="sxs-lookup"><span data-stu-id="2ae43-108">The scenario is made up of 4 pieces:</span></span>  
  
-   <span data-ttu-id="2ae43-109">Servicio de la librería</span><span class="sxs-lookup"><span data-stu-id="2ae43-109">BookStore service</span></span>  
  
-   <span data-ttu-id="2ae43-110">STS BookStore</span><span class="sxs-lookup"><span data-stu-id="2ae43-110">BookStore STS</span></span>  
  
-   <span data-ttu-id="2ae43-111">STS HomeRealm </span><span class="sxs-lookup"><span data-stu-id="2ae43-111">HomeRealm STS</span></span>  
  
-   <span data-ttu-id="2ae43-112">Cliente de librería</span><span class="sxs-lookup"><span data-stu-id="2ae43-112">BookStore Client</span></span>  
  
 <span data-ttu-id="2ae43-113">El servicio de librería admite dos operaciones, `BrowseBooks` y `BuyBook`.</span><span class="sxs-lookup"><span data-stu-id="2ae43-113">The BookStore service supports two operations, `BrowseBooks` and `BuyBook`.</span></span> <span data-ttu-id="2ae43-114">Permite el acceso anónimo a la operación `BrowseBooks`, pero requiere acceso autenticado para tener acceso a la operación `BuyBooks`.</span><span class="sxs-lookup"><span data-stu-id="2ae43-114">It allows anonymous access to the `BrowseBooks` operation, but requires authenticated access to access the `BuyBooks` operation.</span></span> <span data-ttu-id="2ae43-115">La autenticación toma el formulario de un token emitido por el STS BookStore.</span><span class="sxs-lookup"><span data-stu-id="2ae43-115">The authentication takes the form of a token issued by the BookStore STS.</span></span> <span data-ttu-id="2ae43-116">El archivo de configuración para el Servicio de librería dirige los clientes a la STS BookStore mediante `wsFederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="2ae43-116">The configuration file for the BookStore Service points clients to the BookStore STS using the `wsFederationHttpBinding`.</span></span>  
  
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
  
 <span data-ttu-id="2ae43-117">STS BookStore requiere a continuación que los clientes se autentiquen mediante un token emitido por el STS HomeRealm.</span><span class="sxs-lookup"><span data-stu-id="2ae43-117">The BookStore STS then requires that clients authenticate using a token issued by the HomeRealm STS.</span></span> <span data-ttu-id="2ae43-118">De nuevo, el archivo de configuración para el STS BookStore dirige los clientes al STS HomeRealm mediante `wsFederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="2ae43-118">Again, the configuration file for the BookStore STS points clients to the HomeRealm STS using the `wsFederationHttpBinding`.</span></span>  
  
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
  
 <span data-ttu-id="2ae43-119">La secuencia de eventos, al tener acceso a la operación `BuyBook`, es como sigue:</span><span class="sxs-lookup"><span data-stu-id="2ae43-119">The sequence of events when accessing the `BuyBook` operation is as follows:</span></span>  
  
1.  <span data-ttu-id="2ae43-120">El cliente autentica el STS HomeRealm mediante las credenciales de Windows.</span><span class="sxs-lookup"><span data-stu-id="2ae43-120">The client authenticates to the HomeRealm STS using Windows credentials.</span></span>  
  
2.  <span data-ttu-id="2ae43-121">El STS HomeRealm emite un token que se puede utilizar para autenticar el STS BookStore.</span><span class="sxs-lookup"><span data-stu-id="2ae43-121">The HomeRealm STS issues a token that can be used to authenticate to the BookStore STS.</span></span>  
  
3.  <span data-ttu-id="2ae43-122">El cliente autentica el STS BookStore mediante el token emitido por el STS HomeRealm.</span><span class="sxs-lookup"><span data-stu-id="2ae43-122">The client authenticates to the BookStore STS using the token issued by the HomeRealm STS.</span></span>  
  
4.  <span data-ttu-id="2ae43-123">El STS BookStore emite un token que se puede utilizar para autenticar el servicio BookStore.</span><span class="sxs-lookup"><span data-stu-id="2ae43-123">The BookStore STS issues a token that can be used to authenticate to the BookStore Service.</span></span>  
  
5.  <span data-ttu-id="2ae43-124">El cliente autentica el servicio de BookStore mediante el token emitido por el STS BookStore.</span><span class="sxs-lookup"><span data-stu-id="2ae43-124">The client authenticates to the BookStore service using the token issued by the BookStore STS.</span></span>  
  
6.  <span data-ttu-id="2ae43-125">El cliente tiene acceso a la operación `BuyBook`.</span><span class="sxs-lookup"><span data-stu-id="2ae43-125">The client accesses the `BuyBook` operation.</span></span>  
  
 <span data-ttu-id="2ae43-126">Vea las instrucciones siguientes acerca de cómo configurar y ejecutar este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="2ae43-126">See the following instructions about how to set up and run this sample.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2ae43-127">Debe tener permisos de escritura en el **wwwroot** directorio para ejecutar este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="2ae43-127">You must have Write permissions to the **wwwroot** directory to run this sample.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="2ae43-128">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="2ae43-128">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="2ae43-129">Abra la ventana de comandos de SDK.</span><span class="sxs-lookup"><span data-stu-id="2ae43-129">Open the SDK command window.</span></span> <span data-ttu-id="2ae43-130">En la ruta de acceso del ejemplo, ejecute Setup.bat.</span><span class="sxs-lookup"><span data-stu-id="2ae43-130">In the sample path, run Setup.bat.</span></span> <span data-ttu-id="2ae43-131">Esto crea directorios virtuales requeridos para obtener el ejemplo e instala los certificados necesarios con permisos adecuados.</span><span class="sxs-lookup"><span data-stu-id="2ae43-131">This creates the virtual directories required for the sample and installs the required certificates with appropriate permissions.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2ae43-132">El archivo por lotes Setup.bat está diseñado para ejecutarse desde el símbolo del sistema de Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="2ae43-132">The Setup.bat batch file is designed to be run from a Windows SDK Command Prompt.</span></span> <span data-ttu-id="2ae43-133">Requiere que la variable de entorno de MSSDK se dirija al directorio donde está instalado el SDK.</span><span class="sxs-lookup"><span data-stu-id="2ae43-133">It requires that the MSSDK environment variable point to the directory where the SDK is installed.</span></span> <span data-ttu-id="2ae43-134">Esta variable de entorno se establece automáticamente dentro de un símbolo del sistema de Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="2ae43-134">This environment variable is automatically set within a Windows SDK Command Prompt.</span></span> <span data-ttu-id="2ae43-135">En [!INCLUDE[wv](../../../../includes/wv-md.md)], debe asegurarse de que esté instalada la Compatibilidad con la administración de IIS 6.0, porque la instalación utiliza los scripts de administrador de IIS.</span><span class="sxs-lookup"><span data-stu-id="2ae43-135">On [!INCLUDE[wv](../../../../includes/wv-md.md)], you must ensure that IIS 6.0 Management Compatibility is installed because the set up uses IIS administrator scripts.</span></span> <span data-ttu-id="2ae43-136">Al ejecutar el script de instalación en [!INCLUDE[wv](../../../../includes/wv-md.md)], se requieren privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="2ae43-136">Running the set-up script on [!INCLUDE[wv](../../../../includes/wv-md.md)] requires administrator privileges.</span></span>  
  
2.  <span data-ttu-id="2ae43-137">Abra FederationSample.sln en Visual Studio y seleccione **compilar solución** desde el **compilar** menú.</span><span class="sxs-lookup"><span data-stu-id="2ae43-137">Open FederationSample.sln in Visual Studio and select **Build Solution** from the **Build** menu.</span></span> <span data-ttu-id="2ae43-138">De esta forma se compilan los archivos de proyecto comunes, servicio Bookstore, STS Bookstore, STS HomeRealm, y los implementa en IIS.</span><span class="sxs-lookup"><span data-stu-id="2ae43-138">This builds the common project files, Bookstore service, Bookstore STS, HomeRealm STS, and deploys them in IIS.</span></span> <span data-ttu-id="2ae43-139">De esta forma también se compila la aplicación cliente Bookstore y coloca el BookStoreClient.exe ejecutable en la carpeta FederationSample\BookStoreClient\bin\Debug.</span><span class="sxs-lookup"><span data-stu-id="2ae43-139">This also builds the Bookstore client application and places the executable BookStoreClient.exe in the FederationSample\BookStoreClient\bin\Debug folder.</span></span>  
  
3.  <span data-ttu-id="2ae43-140">Haga doble clic en BookStoreClient.exe.</span><span class="sxs-lookup"><span data-stu-id="2ae43-140">Double-click BookStoreClient.exe.</span></span> <span data-ttu-id="2ae43-141">Se muestra la ventana BookStoreClient.</span><span class="sxs-lookup"><span data-stu-id="2ae43-141">The BookStoreClient window is displayed.</span></span>  
  
4.  <span data-ttu-id="2ae43-142">Puede examinar los libros disponibles en la librería haciendo **examinar libros**.</span><span class="sxs-lookup"><span data-stu-id="2ae43-142">You can browse the books available in the bookstore by clicking **Browse Books**.</span></span>  
  
5.  <span data-ttu-id="2ae43-143">Para comprar un libro determinado, seleccione el libro en la lista y haga clic en **comprar libro**.</span><span class="sxs-lookup"><span data-stu-id="2ae43-143">To purchase a particular book, select the book in the list and click **Buy Book**.</span></span> <span data-ttu-id="2ae43-144">La aplicación se inicia y autentica mediante la autenticación de Windows con el Servicio de token de seguridad de HomeRealm.</span><span class="sxs-lookup"><span data-stu-id="2ae43-144">The application starts up and authenticates using Windows authentication with the HomeRealm Security Token Service.</span></span>  
  
     <span data-ttu-id="2ae43-145">El ejemplo se configura para permitirles a los usuarios comprar libros que cuesten 15$ o menos.</span><span class="sxs-lookup"><span data-stu-id="2ae43-145">The sample is configured to allow users to purchase books that cost $15 or less.</span></span> <span data-ttu-id="2ae43-146">Intentar comprar libros que cuesten más de 15 $ provoca que el cliente reciba un mensaje de acceso denegado en el servicio de almacén de libros.</span><span class="sxs-lookup"><span data-stu-id="2ae43-146">Attempting to buy books that cost more than $15 results in the client getting an Access Denied message from the Book Store Service.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2ae43-147">El ejemplo no actualiza el límite de crédito del usuario después de una compra.</span><span class="sxs-lookup"><span data-stu-id="2ae43-147">The sample does not update the user’s credit limit after a purchase.</span></span> <span data-ttu-id="2ae43-148">Puede comprar repetidamente libros dentro del límite de crédito del usuario (fijo).</span><span class="sxs-lookup"><span data-stu-id="2ae43-148">You can repeatedly purchase books within the user’s (fixed) credit limit.</span></span>  
  
#### <a name="to-clean-up"></a><span data-ttu-id="2ae43-149">Para realizar una limpieza</span><span class="sxs-lookup"><span data-stu-id="2ae43-149">To clean up</span></span>  
  
1.  <span data-ttu-id="2ae43-150">Ejecute Cleanup.bat.</span><span class="sxs-lookup"><span data-stu-id="2ae43-150">Run Cleanup.bat.</span></span> <span data-ttu-id="2ae43-151">De esta forma se eliminan los directorios virtuales que se crearon durante la instalación y también se quitan los certificados instalados durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="2ae43-151">This deletes the virtual directories that were created during set up and also removes the certificates installed during setup.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2ae43-152">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="2ae43-152">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2ae43-153">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="2ae43-153">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="2ae43-154">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="2ae43-154">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2ae43-155">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="2ae43-155">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\Federation`  
  
## <a name="see-also"></a><span data-ttu-id="2ae43-156">Vea también</span><span class="sxs-lookup"><span data-stu-id="2ae43-156">See Also</span></span>
