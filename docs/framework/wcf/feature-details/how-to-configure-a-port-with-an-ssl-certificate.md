---
title: Filtrar para configurar un puerto con un certificado SSL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SSL
- WCF, security mode
- WCF, security
ms.assetid: b8abcc8e-a5f5-4317-aca5-01e3c40ab24d
ms.openlocfilehash: d709123895f361c1d2268a218b4163c8d195e1b4
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59345591"
---
# <a name="how-to-configure-a-port-with-an-ssl-certificate"></a><span data-ttu-id="37ed1-102">Filtrar para configurar un puerto con un certificado SSL</span><span class="sxs-lookup"><span data-stu-id="37ed1-102">How to: Configure a Port with an SSL Certificate</span></span>
<span data-ttu-id="37ed1-103">Al crear un servicio de Windows Communication Foundation (WCF) alojados en sí mismos con el <xref:System.ServiceModel.WSHttpBinding> que utiliza seguridad de transporte de clase, también debe configurar un puerto con un certificado X.509.</span><span class="sxs-lookup"><span data-stu-id="37ed1-103">When creating a self-hosted Windows Communication Foundation (WCF) service with the <xref:System.ServiceModel.WSHttpBinding> class that uses transport security, you must also configure a port with an X.509 certificate.</span></span> <span data-ttu-id="37ed1-104">Si no está creando un servicio autohospedado, puede hospedar su servicio en Servicios de Internet Information Server (IIS).</span><span class="sxs-lookup"><span data-stu-id="37ed1-104">If you are not creating a self-hosted service, you can host your service on Internet Information Services (IIS).</span></span> <span data-ttu-id="37ed1-105">Para obtener más información, consulte [seguridad de transporte HTTP](../../../../docs/framework/wcf/feature-details/http-transport-security.md).</span><span class="sxs-lookup"><span data-stu-id="37ed1-105">For more information, see [HTTP Transport Security](../../../../docs/framework/wcf/feature-details/http-transport-security.md).</span></span>  
  
 <span data-ttu-id="37ed1-106">La herramienta que se usa para configurar un puerto depende del sistema operativo que se esté ejecutando en el equipo.</span><span class="sxs-lookup"><span data-stu-id="37ed1-106">To configure a port, the tool you use depends on the operating system that is running on your machine.</span></span>  
  
 <span data-ttu-id="37ed1-107">Si está ejecutando [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] o [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use la herramienta HttpCfg.exe.</span><span class="sxs-lookup"><span data-stu-id="37ed1-107">If you are running [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use the HttpCfg.exe tool.</span></span> <span data-ttu-id="37ed1-108">Esta herramienta se instala con [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)].</span><span class="sxs-lookup"><span data-stu-id="37ed1-108">With [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] this tool is installed.</span></span> <span data-ttu-id="37ed1-109">Con [!INCLUDE[wxp](../../../../includes/wxp-md.md)], puede descargar la herramienta en [Windows XP Service Pack 2 Support Tools](https://go.microsoft.com/fwlink/?LinkId=88606).</span><span class="sxs-lookup"><span data-stu-id="37ed1-109">With [!INCLUDE[wxp](../../../../includes/wxp-md.md)], you can download the tool at [Windows XP Service Pack 2 Support Tools](https://go.microsoft.com/fwlink/?LinkId=88606).</span></span> <span data-ttu-id="37ed1-110">Para obtener más información, consulte [introducción general a Httpcfg](https://go.microsoft.com/fwlink/?LinkId=88605).</span><span class="sxs-lookup"><span data-stu-id="37ed1-110">For more information, see [Httpcfg Overview](https://go.microsoft.com/fwlink/?LinkId=88605).</span></span> <span data-ttu-id="37ed1-111">El [documentación de las herramientas de soporte técnico de Windows](https://go.microsoft.com/fwlink/?LinkId=94840) explica la sintaxis de la herramienta Httpcfg.exe.</span><span class="sxs-lookup"><span data-stu-id="37ed1-111">The [Windows Support Tools documentation](https://go.microsoft.com/fwlink/?LinkId=94840) explains the syntax for the Httpcfg.exe tool.</span></span>  
  
 <span data-ttu-id="37ed1-112">Si está ejecutando [!INCLUDE[wv](../../../../includes/wv-md.md)], use la herramienta Netsh.exe, que ya está instalada.</span><span class="sxs-lookup"><span data-stu-id="37ed1-112">If you are running [!INCLUDE[wv](../../../../includes/wv-md.md)], use the Netsh.exe tool that is already installed.</span></span>  
  
 <span data-ttu-id="37ed1-113">En este tema se describe cómo se realizan varios procedimientos:</span><span class="sxs-lookup"><span data-stu-id="37ed1-113">This topic describes how to accomplish several procedures:</span></span>  
  
-   <span data-ttu-id="37ed1-114">Determinar la configuración de puerto actual de un equipo.</span><span class="sxs-lookup"><span data-stu-id="37ed1-114">Determining a computer's current port configuration.</span></span>  
  
-   <span data-ttu-id="37ed1-115">Obtener la huella digital de un certificado (necesario para los dos procedimientos siguientes).</span><span class="sxs-lookup"><span data-stu-id="37ed1-115">Getting a certificate's thumbprint (necessary for the following two procedures).</span></span>  
  
-   <span data-ttu-id="37ed1-116">Enlazar un certificado SSL a una configuración de puerto.</span><span class="sxs-lookup"><span data-stu-id="37ed1-116">Binding an SSL certificate to a port configuration.</span></span>  
  
-   <span data-ttu-id="37ed1-117">Enlazar un certificado SSL a una configuración del puerto y admitir los certificados de cliente.</span><span class="sxs-lookup"><span data-stu-id="37ed1-117">Binding an SSL certificate to a port configuration and supporting client certificates.</span></span>  
  
-   <span data-ttu-id="37ed1-118">Eliminar un certificado SSL de un número de puerto.</span><span class="sxs-lookup"><span data-stu-id="37ed1-118">Deleting an SSL certificate from a port number.</span></span>  
  
 <span data-ttu-id="37ed1-119">Tenga en cuenta que para modificar los certificados almacenados en el equipo se requieren privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="37ed1-119">Note that modifying certificates stored on the computer requires administrative privileges.</span></span>  
  
### <a name="to-determine-how-ports-are-configured"></a><span data-ttu-id="37ed1-120">Determinar cómo se configuran los puertos</span><span class="sxs-lookup"><span data-stu-id="37ed1-120">To determine how ports are configured</span></span>  
  
1. <span data-ttu-id="37ed1-121">En [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] o [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use la herramienta HttpCfg.exe para ver la configuración de puerto actual, utilizando el **consulta** y **ssl** se activa, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="37ed1-121">In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use the HttpCfg.exe tool to view the current port configuration, using the **query** and **ssl** switches, as shown in the following example.</span></span>  
  
    ```  
    httpcfg query ssl  
    ```  
  
2. <span data-ttu-id="37ed1-122">En [!INCLUDE[wv](../../../../includes/wv-md.md)], use la herramienta Netsh.exe para ver la configuración de puerto actual, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="37ed1-122">In [!INCLUDE[wv](../../../../includes/wv-md.md)], use the Netsh.exe tool to view the current port configuration, as shown in the following example.</span></span>  
  
    ```  
    netsh http show sslcert  
    ```  
  
### <a name="to-get-a-certificates-thumbprint"></a><span data-ttu-id="37ed1-123">Para obtener una huella digital de un certificado</span><span class="sxs-lookup"><span data-stu-id="37ed1-123">To get a certificate's thumbprint</span></span>  
  
1. <span data-ttu-id="37ed1-124">Use el complemento de certificados de MMC para buscar un certificado X.509 que tenga como finalidad la autenticación del cliente.</span><span class="sxs-lookup"><span data-stu-id="37ed1-124">Use the Certificates MMC snap-in to find an X.509 certificate that has an intended purpose of client authentication.</span></span> <span data-ttu-id="37ed1-125">Para obtener más información, vea [Cómo: Ver certificados con el complemento de MMC](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="37ed1-125">For more information, see [How to: View Certificates with the MMC Snap-in](../../../../docs/framework/wcf/feature-details/how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>  
  
2. <span data-ttu-id="37ed1-126">Obtenga acceso a la huella digital del certificado.</span><span class="sxs-lookup"><span data-stu-id="37ed1-126">Access the certificate's thumbprint.</span></span> <span data-ttu-id="37ed1-127">Para obtener más información, vea [Cómo: Recuperar la huella digital de un certificado](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="37ed1-127">For more information, see [How to: Retrieve the Thumbprint of a Certificate](../../../../docs/framework/wcf/feature-details/how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
3. <span data-ttu-id="37ed1-128">Copie la huella digital del certificado en un editor de texto, como por ejemplo Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="37ed1-128">Copy the thumbprint of the certificate into a text editor, such as Notepad.</span></span>  
  
4. <span data-ttu-id="37ed1-129">Quite todos los espacios entre los caracteres hexadecimales.</span><span class="sxs-lookup"><span data-stu-id="37ed1-129">Remove all spaces between the hexadecimal characters.</span></span> <span data-ttu-id="37ed1-130">Una manera de llevarlo a cabo es utilizar la característica del editor de texto buscar y reemplazar y reemplazar todos los espacios con un carácter nulo.</span><span class="sxs-lookup"><span data-stu-id="37ed1-130">One way to accomplish this is to use the text editor's find-and-replace feature and replace each space with a null character.</span></span>  
  
### <a name="to-bind-an-ssl-certificate-to-a-port-number"></a><span data-ttu-id="37ed1-131">Enlazar un Certificado SSL a un número de puerto</span><span class="sxs-lookup"><span data-stu-id="37ed1-131">To bind an SSL certificate to a port number</span></span>  
  
1. <span data-ttu-id="37ed1-132">En [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] o [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use la herramienta HttpCfg.exe en modo "set" en el almacén SSL (Capa de sockets seguros) para enlazar el certificado a un número de puerto.</span><span class="sxs-lookup"><span data-stu-id="37ed1-132">In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use the HttpCfg.exe tool in "set" mode on the Secure Sockets Layer (SSL) store to bind the certificate to a port number.</span></span> <span data-ttu-id="37ed1-133">La herramienta utiliza la huella digital para identificar el certificado, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="37ed1-133">The tool uses the thumbprint to identify the certificate, as shown in the following example.</span></span>  
  
    ```  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
    -   <span data-ttu-id="37ed1-134">El **-i** conmutador tiene la sintaxis de `IP`:`port` e indica a la herramienta para establecer el certificado en el puerto 8012 del equipo.</span><span class="sxs-lookup"><span data-stu-id="37ed1-134">The **-i** switch has the syntax of `IP`:`port` and instructs the tool to set the certificate to port 8012 of the computer.</span></span> <span data-ttu-id="37ed1-135">De forma opcional, también se pueden reemplazar los cuatro ceros que preceden el número por la dirección IP real del equipo.</span><span class="sxs-lookup"><span data-stu-id="37ed1-135">Optionally, the four zeroes that precede the number can also be replaced by the actual IP address of the computer.</span></span>  
  
    -   <span data-ttu-id="37ed1-136">El **-h** conmutador especifica la huella digital del certificado.</span><span class="sxs-lookup"><span data-stu-id="37ed1-136">The **-h** switch specifies the thumbprint of the certificate.</span></span>  
  
2. <span data-ttu-id="37ed1-137">En [!INCLUDE[wv](../../../../includes/wv-md.md)], use la herramienta Netsh.exe, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="37ed1-137">In [!INCLUDE[wv](../../../../includes/wv-md.md)], use the Netsh.exe tool, as shown in the following example.</span></span>  
  
    ```  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF}   
    ```  
  
    -   <span data-ttu-id="37ed1-138">El **certhash** parámetro especifica la huella digital del certificado.</span><span class="sxs-lookup"><span data-stu-id="37ed1-138">The **certhash** parameter specifies the thumbprint of the certificate.</span></span>  
  
    -   <span data-ttu-id="37ed1-139">El **ipport** parámetro especifica la dirección IP y puerto, y funciona exactamente igual que el **-i** switch de la herramienta Httpcfg.exe descrita.</span><span class="sxs-lookup"><span data-stu-id="37ed1-139">The **ipport** parameter specifies the IP address and port, and functions just like the **-i** switch of the Httpcfg.exe tool described.</span></span>  
  
    -   <span data-ttu-id="37ed1-140">El **appid** parámetro es un GUID que se puede usar para identificar la aplicación propietaria.</span><span class="sxs-lookup"><span data-stu-id="37ed1-140">The **appid** parameter is a GUID that can be used to identify the owning application.</span></span>  
  
### <a name="to-bind-an-ssl-certificate-to-a-port-number-and-support-client-certificates"></a><span data-ttu-id="37ed1-141">Para enlazar un Certificado SSL a un número de puerto y a certificados de cliente de compatibilidad</span><span class="sxs-lookup"><span data-stu-id="37ed1-141">To bind an SSL certificate to a port number and support client certificates</span></span>  
  
1. <span data-ttu-id="37ed1-142">En [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] o [!INCLUDE[wxp](../../../../includes/wxp-md.md)], para admitir clientes que se autentican con certificados X.509 en el nivel de transporte, siga el procedimiento anterior pero pase un parámetro de línea de comandos adicional a HttpCfg.exe, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="37ed1-142">In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], to support clients that authenticate with X.509 certificates at the transport layer, follow the preceding procedure but pass an additional command-line parameter to HttpCfg.exe, as shown in the following example.</span></span>  
  
    ```  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6 -f 2  
    ```  
  
     <span data-ttu-id="37ed1-143">El **-f** conmutador tiene la sintaxis de `n` donde n es un número entre 1 y 7.</span><span class="sxs-lookup"><span data-stu-id="37ed1-143">The **-f** switch has the syntax of `n` where n is a number between 1 and 7.</span></span> <span data-ttu-id="37ed1-144">El valor 2, como se mostraba en el ejemplo anterior, habilita los certificados de cliente en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="37ed1-144">A value of 2, as shown in the preceding example, enables client certificates at the transport layer.</span></span> <span data-ttu-id="37ed1-145">El valor 3 habilita los certificados de cliente y los asigna a una cuenta de Windows.</span><span class="sxs-lookup"><span data-stu-id="37ed1-145">A value of 3 enables client certificates and maps those certificates to a Windows account.</span></span> <span data-ttu-id="37ed1-146">Consulte la Ayuda HttpCfg.exe para el comportamiento de otros valores.</span><span class="sxs-lookup"><span data-stu-id="37ed1-146">See HttpCfg.exe Help for the behavior of other values.</span></span>  
  
2. <span data-ttu-id="37ed1-147">En [!INCLUDE[wv](../../../../includes/wv-md.md)], para admitir los clientes que se autentican con certificados X.509 en el nivel de transporte, siga el procedimiento anterior pero pase un parámetro de línea de comandos adicional a HttpCfg.exe, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="37ed1-147">In [!INCLUDE[wv](../../../../includes/wv-md.md)], to support clients that authenticate with X.509 certificates at the transport layer, follow the preceding procedure, but with an additional parameter, as shown in the following example.</span></span>  
  
    ```  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF} clientcertnegotiation=enable  
    ```  
  
### <a name="to-delete-an-ssl-certificate-from-a-port-number"></a><span data-ttu-id="37ed1-148">Eliminar un Certificado SSL desde un número de puerto</span><span class="sxs-lookup"><span data-stu-id="37ed1-148">To delete an SSL certificate from a port number</span></span>  
  
1. <span data-ttu-id="37ed1-149">Use la herramienta HttpCfg.exe o Netsh.exe para ver los puertos y huellas digitales de todos los enlaces del equipo.</span><span class="sxs-lookup"><span data-stu-id="37ed1-149">Use the HttpCfg.exe or Netsh.exe tool to see the ports and thumbprints of all bindings on the computer.</span></span> <span data-ttu-id="37ed1-150">Para imprimir la información en el disco, use el carácter de redirección ">", como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="37ed1-150">To print the information to disk, use the redirection character ">", as shown in the following example.</span></span>  
  
    ```  
    httpcfg query ssl>myMachinePorts.txt  
    ```  
  
2. <span data-ttu-id="37ed1-151">En [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] o [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use la herramienta HttpCfg.exe con las **eliminar** y **ssl** palabras clave.</span><span class="sxs-lookup"><span data-stu-id="37ed1-151">In [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] or [!INCLUDE[wxp](../../../../includes/wxp-md.md)], use the HttpCfg.exe tool with the **delete** and **ssl** keywords.</span></span> <span data-ttu-id="37ed1-152">Use la **-i** modificador para especificar el `IP`:`port` número y el **-h** conmutador para especificar la huella digital.</span><span class="sxs-lookup"><span data-stu-id="37ed1-152">Use the **-i** switch to specify the `IP`:`port` number, and the **-h** switch to specify the thumbprint.</span></span>  
  
    ```  
    httpcfg delete ssl -i 0.0.0.0:8005 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
3. <span data-ttu-id="37ed1-153">En [!INCLUDE[wv](../../../../includes/wv-md.md)], use la herramienta Netsh.exe, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="37ed1-153">In [!INCLUDE[wv](../../../../includes/wv-md.md)], use the Netsh.exe tool, as shown in the following example.</span></span>  
  
    ```  
    Netsh http delete sslcert ipport=0.0.0.0:8005  
    ```  
  
## <a name="example"></a><span data-ttu-id="37ed1-154">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="37ed1-154">Example</span></span>  
 <span data-ttu-id="37ed1-155">El código siguiente muestra cómo crear un servicio autohospedado utilizando la clase <xref:System.ServiceModel.WSHttpBinding> establezca para seguridad de transporte.</span><span class="sxs-lookup"><span data-stu-id="37ed1-155">The following code shows how to create a self-hosted service using the <xref:System.ServiceModel.WSHttpBinding> class set to transport security.</span></span> <span data-ttu-id="37ed1-156">Cuando cree una aplicación, especifique el número de puerto en la dirección.</span><span class="sxs-lookup"><span data-stu-id="37ed1-156">When creating an application, specify the port number in the address.</span></span>  
  
 [!code-csharp[c_WsHttpService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wshttpservice/cs/source.cs#3)]
 [!code-vb[c_WsHttpService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wshttpservice/vb/source.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="37ed1-157">Vea también</span><span class="sxs-lookup"><span data-stu-id="37ed1-157">See also</span></span>

- [<span data-ttu-id="37ed1-158">Seguridad de transporte HTTP</span><span class="sxs-lookup"><span data-stu-id="37ed1-158">HTTP Transport Security</span></span>](../../../../docs/framework/wcf/feature-details/http-transport-security.md)
