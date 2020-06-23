---
title: Procedimiento para configurar un puerto con un certificado SSL
description: Obtenga información sobre cómo configurar un puerto con un certificado X. 509, necesario para un servicio WCF autohospedado con la clase WSHttpBinding mediante la seguridad de transporte.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SSL
- WCF, security mode
- WCF, security
ms.assetid: b8abcc8e-a5f5-4317-aca5-01e3c40ab24d
ms.openlocfilehash: 0eccdf916dae7b886cbc4e6563e6dfe17039c321
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247187"
---
# <a name="how-to-configure-a-port-with-an-ssl-certificate"></a><span data-ttu-id="29088-103">Procedimiento para configurar un puerto con un certificado SSL</span><span class="sxs-lookup"><span data-stu-id="29088-103">How to: Configure a Port with an SSL Certificate</span></span>

<span data-ttu-id="29088-104">Al crear un servicio de Windows Communication Foundation (WCF) autohospedado con la <xref:System.ServiceModel.WSHttpBinding> clase que usa la seguridad de transporte, también debe configurar un puerto con un certificado X. 509.</span><span class="sxs-lookup"><span data-stu-id="29088-104">When creating a self-hosted Windows Communication Foundation (WCF) service with the <xref:System.ServiceModel.WSHttpBinding> class that uses transport security, you must also configure a port with an X.509 certificate.</span></span> <span data-ttu-id="29088-105">Si no está creando un servicio autohospedado, puede hospedar su servicio en Servicios de Internet Information Server (IIS).</span><span class="sxs-lookup"><span data-stu-id="29088-105">If you are not creating a self-hosted service, you can host your service on Internet Information Services (IIS).</span></span> <span data-ttu-id="29088-106">Para obtener más información, vea [seguridad de transporte http](http-transport-security.md).</span><span class="sxs-lookup"><span data-stu-id="29088-106">For more information, see [HTTP Transport Security](http-transport-security.md).</span></span>  
  
 <span data-ttu-id="29088-107">La herramienta que se usa para configurar un puerto depende del sistema operativo que se esté ejecutando en el equipo.</span><span class="sxs-lookup"><span data-stu-id="29088-107">To configure a port, the tool you use depends on the operating system that is running on your machine.</span></span>  
  
 <span data-ttu-id="29088-108">Si está ejecutando Windows Server 2003, use la herramienta HttpCfg.exe.</span><span class="sxs-lookup"><span data-stu-id="29088-108">If you are running Windows Server 2003, use the HttpCfg.exe tool.</span></span> <span data-ttu-id="29088-109">En Windows Server 2003, esta herramienta está instalada.</span><span class="sxs-lookup"><span data-stu-id="29088-109">On Windows Server 2003, this tool is installed.</span></span> <span data-ttu-id="29088-110">Para obtener más información, consulte [información general de Httpcfg](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc787508(v=ws.10)).</span><span class="sxs-lookup"><span data-stu-id="29088-110">For more information, see [Httpcfg Overview](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc787508(v=ws.10)).</span></span> <span data-ttu-id="29088-111">La [documentación](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc781601(v=ws.10)) de las herramientas de soporte de Windows explica la sintaxis de la herramienta Httpcfg.exe.</span><span class="sxs-lookup"><span data-stu-id="29088-111">The [Windows Support Tools documentation](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2003/cc781601(v=ws.10)) explains the syntax for the Httpcfg.exe tool.</span></span>  
  
 <span data-ttu-id="29088-112">Si está ejecutando Windows Vista, use la herramienta de Netsh.exe que ya está instalada.</span><span class="sxs-lookup"><span data-stu-id="29088-112">If you are running Windows Vista, use the Netsh.exe tool that is already installed.</span></span>
  
> [!NOTE]
> <span data-ttu-id="29088-113">La modificación de los certificados almacenados en el equipo requiere privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="29088-113">Modifying certificates stored on the computer requires administrative privileges.</span></span>  
  
## <a name="determine-how-ports-are-configured"></a><span data-ttu-id="29088-114">Determinar cómo se configuran los puertos</span><span class="sxs-lookup"><span data-stu-id="29088-114">Determine how ports are configured</span></span>  
  
1. <span data-ttu-id="29088-115">En Windows Server 2003 o Windows XP, use la herramienta de HttpCfg.exe para ver la configuración de puerto actual, mediante los modificadores de **consulta** y **SSL** , tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="29088-115">In Windows Server 2003 or Windows XP, use the HttpCfg.exe tool to view the current port configuration, using the **query** and **ssl** switches, as shown in the following example.</span></span>  
  
    ```console
    httpcfg query ssl  
    ```  
  
2. <span data-ttu-id="29088-116">En Windows Vista, use la herramienta de Netsh.exe para ver la configuración de puerto actual, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="29088-116">In Windows Vista, use the Netsh.exe tool to view the current port configuration, as shown in the following example.</span></span>  
  
    ```console  
    netsh http show sslcert  
    ```  
  
## <a name="get-a-certificates-thumbprint"></a><span data-ttu-id="29088-117">Obtener la huella digital de un certificado</span><span class="sxs-lookup"><span data-stu-id="29088-117">Get a certificate's thumbprint</span></span>  
  
1. <span data-ttu-id="29088-118">Use el complemento de certificados de MMC para buscar un certificado X.509 que tenga como finalidad la autenticación del cliente.</span><span class="sxs-lookup"><span data-stu-id="29088-118">Use the Certificates MMC snap-in to find an X.509 certificate that has an intended purpose of client authentication.</span></span> <span data-ttu-id="29088-119">Para más información, consulte [Visualización de certificados con el complemento MMC](how-to-view-certificates-with-the-mmc-snap-in.md).</span><span class="sxs-lookup"><span data-stu-id="29088-119">For more information, see [How to: View Certificates with the MMC Snap-in](how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>  
  
2. <span data-ttu-id="29088-120">Obtenga acceso a la huella digital del certificado.</span><span class="sxs-lookup"><span data-stu-id="29088-120">Access the certificate's thumbprint.</span></span> <span data-ttu-id="29088-121">Para más información, consulte [Cómo recuperar la huella digital de un certificado](how-to-retrieve-the-thumbprint-of-a-certificate.md).</span><span class="sxs-lookup"><span data-stu-id="29088-121">For more information, see [How to: Retrieve the Thumbprint of a Certificate](how-to-retrieve-the-thumbprint-of-a-certificate.md).</span></span>  
  
3. <span data-ttu-id="29088-122">Copie la huella digital del certificado en un editor de texto, como por ejemplo Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="29088-122">Copy the thumbprint of the certificate into a text editor, such as Notepad.</span></span>  
  
4. <span data-ttu-id="29088-123">Quite todos los espacios entre los caracteres hexadecimales.</span><span class="sxs-lookup"><span data-stu-id="29088-123">Remove all spaces between the hexadecimal characters.</span></span> <span data-ttu-id="29088-124">Una manera de llevarlo a cabo es utilizar la característica del editor de texto buscar y reemplazar y reemplazar todos los espacios con un carácter nulo.</span><span class="sxs-lookup"><span data-stu-id="29088-124">One way to accomplish this is to use the text editor's find-and-replace feature and replace each space with a null character.</span></span>  
  
## <a name="bind-an-ssl-certificate-to-a-port-number"></a><span data-ttu-id="29088-125">Enlazar un certificado SSL a un número de Puerto</span><span class="sxs-lookup"><span data-stu-id="29088-125">Bind an SSL certificate to a port number</span></span>  
  
1. <span data-ttu-id="29088-126">En Windows Server 2003 o Windows XP, use la herramienta HttpCfg.exe del modo "SET" en el almacén de Capa de sockets seguros (SSL) para enlazar el certificado a un número de puerto.</span><span class="sxs-lookup"><span data-stu-id="29088-126">In Windows Server 2003 or Windows XP, use the HttpCfg.exe tool in "set" mode on the Secure Sockets Layer (SSL) store to bind the certificate to a port number.</span></span> <span data-ttu-id="29088-127">La herramienta utiliza la huella digital para identificar el certificado, tal y como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="29088-127">The tool uses the thumbprint to identify the certificate, as shown in the following example.</span></span>  
  
    ```console  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
    - <span data-ttu-id="29088-128">El modificador **-i** tiene la sintaxis de `IP` : `port` e indica a la herramienta que establezca el certificado en el puerto 8012 del equipo.</span><span class="sxs-lookup"><span data-stu-id="29088-128">The **-i** switch has the syntax of `IP`:`port` and instructs the tool to set the certificate to port 8012 of the computer.</span></span> <span data-ttu-id="29088-129">De forma opcional, también se pueden reemplazar los cuatro ceros que preceden el número por la dirección IP real del equipo.</span><span class="sxs-lookup"><span data-stu-id="29088-129">Optionally, the four zeroes that precede the number can also be replaced by the actual IP address of the computer.</span></span>  
  
    - <span data-ttu-id="29088-130">El modificador **-h** especifica la huella digital del certificado.</span><span class="sxs-lookup"><span data-stu-id="29088-130">The **-h** switch specifies the thumbprint of the certificate.</span></span>  
  
2. <span data-ttu-id="29088-131">En Windows Vista, use la herramienta Netsh.exe, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="29088-131">In Windows Vista, use the Netsh.exe tool, as shown in the following example.</span></span>  
  
    ```console  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF}
    ```  
  
    - <span data-ttu-id="29088-132">El parámetro **certhash** especifica la huella digital del certificado.</span><span class="sxs-lookup"><span data-stu-id="29088-132">The **certhash** parameter specifies the thumbprint of the certificate.</span></span>  
  
    - <span data-ttu-id="29088-133">El parámetro **ipport** especifica la dirección IP y el puerto, y funciona de la misma manera que el modificador **-i** de la herramienta Httpcfg.exe que se describe.</span><span class="sxs-lookup"><span data-stu-id="29088-133">The **ipport** parameter specifies the IP address and port, and functions just like the **-i** switch of the Httpcfg.exe tool described.</span></span>  
  
    - <span data-ttu-id="29088-134">El parámetro **AppID** es un GUID que se puede usar para identificar la aplicación propietaria.</span><span class="sxs-lookup"><span data-stu-id="29088-134">The **appid** parameter is a GUID that can be used to identify the owning application.</span></span>  
  
## <a name="bind-an-ssl-certificate-to-a-port-number-and-support-client-certificates"></a><span data-ttu-id="29088-135">Enlazar un certificado SSL a un número de puerto y certificados de cliente de soporte</span><span class="sxs-lookup"><span data-stu-id="29088-135">Bind an SSL certificate to a port number and support client certificates</span></span>  
  
1. <span data-ttu-id="29088-136">En Windows Server 2003 o Windows XP, para admitir clientes que se autentican con certificados X. 509 en el nivel de transporte, siga el procedimiento anterior pero pase un parámetro de línea de comandos adicional a HttpCfg.exe, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="29088-136">In Windows Server 2003 or Windows XP, to support clients that authenticate with X.509 certificates at the transport layer, follow the preceding procedure but pass an additional command-line parameter to HttpCfg.exe, as shown in the following example.</span></span>  
  
    ```console  
    httpcfg set ssl -i 0.0.0.0:8012 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6 -f 2  
    ```  
  
     <span data-ttu-id="29088-137">El modificador **-f** tiene la sintaxis, `n` donde n es un número entre 1 y 7.</span><span class="sxs-lookup"><span data-stu-id="29088-137">The **-f** switch has the syntax of `n` where n is a number between 1 and 7.</span></span> <span data-ttu-id="29088-138">El valor 2, como se mostraba en el ejemplo anterior, habilita los certificados de cliente en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="29088-138">A value of 2, as shown in the preceding example, enables client certificates at the transport layer.</span></span> <span data-ttu-id="29088-139">El valor 3 habilita los certificados de cliente y los asigna a una cuenta de Windows.</span><span class="sxs-lookup"><span data-stu-id="29088-139">A value of 3 enables client certificates and maps those certificates to a Windows account.</span></span> <span data-ttu-id="29088-140">Consulte la Ayuda HttpCfg.exe para el comportamiento de otros valores.</span><span class="sxs-lookup"><span data-stu-id="29088-140">See HttpCfg.exe Help for the behavior of other values.</span></span>  
  
2. <span data-ttu-id="29088-141">En Windows Vista, para admitir clientes que se autentican con certificados X. 509 en el nivel de transporte, siga el procedimiento anterior, pero con un parámetro adicional, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="29088-141">In Windows Vista, to support clients that authenticate with X.509 certificates at the transport layer, follow the preceding procedure, but with an additional parameter, as shown in the following example.</span></span>  
  
    ```console  
    netsh http add sslcert ipport=0.0.0.0:8000 certhash=0000000000003ed9cd0c315bbb6dc1c08da5e6 appid={00112233-4455-6677-8899-AABBCCDDEEFF} clientcertnegotiation=enable  
    ```  
  
## <a name="delete-an-ssl-certificate-from-a-port-number"></a><span data-ttu-id="29088-142">Eliminar un certificado SSL de un número de Puerto</span><span class="sxs-lookup"><span data-stu-id="29088-142">Delete an SSL certificate from a port number</span></span>  
  
1. <span data-ttu-id="29088-143">Use la herramienta HttpCfg.exe o Netsh.exe para ver los puertos y huellas digitales de todos los enlaces del equipo.</span><span class="sxs-lookup"><span data-stu-id="29088-143">Use the HttpCfg.exe or Netsh.exe tool to see the ports and thumbprints of all bindings on the computer.</span></span> <span data-ttu-id="29088-144">Para imprimir la información en el disco, use el carácter de redireccionamiento ">", como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="29088-144">To print the information to disk, use the redirection character ">", as shown in the following example.</span></span>  
  
    ```console  
    httpcfg query ssl>myMachinePorts.txt  
    ```
  
2. <span data-ttu-id="29088-145">En Windows Server 2003 o Windows XP, use la herramienta de HttpCfg.exe con las palabras clave **Delete** y **SSL** .</span><span class="sxs-lookup"><span data-stu-id="29088-145">In Windows Server 2003 or Windows XP, use the HttpCfg.exe tool with the **delete** and **ssl** keywords.</span></span> <span data-ttu-id="29088-146">Use el modificador **-i** para especificar `IP` el `port` número: y el modificador **-h** para especificar la huella digital.</span><span class="sxs-lookup"><span data-stu-id="29088-146">Use the **-i** switch to specify the `IP`:`port` number, and the **-h** switch to specify the thumbprint.</span></span>  
  
    ```console  
    httpcfg delete ssl -i 0.0.0.0:8005 -h 0000000000003ed9cd0c315bbb6dc1c08da5e6  
    ```  
  
3. <span data-ttu-id="29088-147">En Windows Vista, use la herramienta Netsh.exe, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="29088-147">In Windows Vista, use the Netsh.exe tool, as shown in the following example.</span></span>  
  
    ```console  
    Netsh http delete sslcert ipport=0.0.0.0:8005  
    ```  
  
## <a name="example"></a><span data-ttu-id="29088-148">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="29088-148">Example</span></span>  

 <span data-ttu-id="29088-149">El código siguiente muestra cómo crear un servicio autohospedado utilizando la clase <xref:System.ServiceModel.WSHttpBinding> establezca para seguridad de transporte.</span><span class="sxs-lookup"><span data-stu-id="29088-149">The following code shows how to create a self-hosted service using the <xref:System.ServiceModel.WSHttpBinding> class set to transport security.</span></span> <span data-ttu-id="29088-150">Cuando cree una aplicación, especifique el número de puerto en la dirección.</span><span class="sxs-lookup"><span data-stu-id="29088-150">When creating an application, specify the port number in the address.</span></span>  
  
 [!code-csharp[c_WsHttpService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wshttpservice/cs/source.cs#3)]
 [!code-vb[c_WsHttpService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wshttpservice/vb/source.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="29088-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="29088-151">See also</span></span>

- [<span data-ttu-id="29088-152">Seguridad de transporte HTTP</span><span class="sxs-lookup"><span data-stu-id="29088-152">HTTP Transport Security</span></span>](http-transport-security.md)
