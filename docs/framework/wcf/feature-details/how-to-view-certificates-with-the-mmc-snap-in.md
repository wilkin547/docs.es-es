---
title: Procedimiento Ver certificados con el complemento de MMC
ms.date: 02/25/2019
helpviewer_keywords:
- certificates [WCF], viewing with the MMC snap-in
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
ms.openlocfilehash: 69f79b64250ff46524e7b4720d13351774875a3f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59167510"
---
# <a name="how-to-view-certificates-with-the-mmc-snap-in"></a><span data-ttu-id="7602c-102">Procedimiento Ver certificados con el complemento de MMC</span><span class="sxs-lookup"><span data-stu-id="7602c-102">How to: View certificates with the MMC snap-in</span></span>
<span data-ttu-id="7602c-103">Cuando se crea un cliente segura o el servicio, puede usar un [certificado](working-with-certificates.md) como la credencial.</span><span class="sxs-lookup"><span data-stu-id="7602c-103">When you create a secure client or service, you can use a [certificate](working-with-certificates.md) as the credential.</span></span> <span data-ttu-id="7602c-104">Por ejemplo, un tipo común de credencial es el certificado X.509, que se crea con el <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="7602c-104">For example, a common type of credential is the X.509 certificate, which you create with the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType> method.</span></span> 

<span data-ttu-id="7602c-105">Hay tres tipos diferentes de almacenes de certificados que se pueden examinar con Microsoft Management Console (MMC) en los sistemas de Windows:</span><span class="sxs-lookup"><span data-stu-id="7602c-105">There are three different types of certificate stores that you can examine with the Microsoft Management Console (MMC) on Windows systems:</span></span>

- <span data-ttu-id="7602c-106">Equipo local: El almacén es local en el dispositivo y global para todos los usuarios en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7602c-106">Local computer: The store is local to the device and global to all users on the device.</span></span>

- <span data-ttu-id="7602c-107">Usuario actual: El almacén es local para la cuenta de usuario actual en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="7602c-107">Current user: The store is local to the current user account on the device.</span></span>

- <span data-ttu-id="7602c-108">Cuenta de servicio: El almacén es un servicio determinado en el dispositivo local.</span><span class="sxs-lookup"><span data-stu-id="7602c-108">Service account: The store is local to a particular service on the device.</span></span>

## <a name="view-certificates-in-the-mmc-snap-in"></a><span data-ttu-id="7602c-109">Ver los certificados en el complemento MMC</span><span class="sxs-lookup"><span data-stu-id="7602c-109">View certificates in the MMC snap-in</span></span> 

<span data-ttu-id="7602c-110">El siguiente procedimiento muestra cómo examinar los almacenes en el dispositivo local para buscar un certificado adecuado:</span><span class="sxs-lookup"><span data-stu-id="7602c-110">The following procedure demonstrates how to examine the stores on your local device to find an appropriate certificate:</span></span> 
  
1. <span data-ttu-id="7602c-111">Seleccione **ejecutar** desde el **iniciar** menú y, a continuación, escriba *mmc*.</span><span class="sxs-lookup"><span data-stu-id="7602c-111">Select **Run** from the **Start** menu, and then enter *mmc*.</span></span> 

    <span data-ttu-id="7602c-112">Aparece la consola MMC.</span><span class="sxs-lookup"><span data-stu-id="7602c-112">The MMC appears.</span></span> 
  
2. <span data-ttu-id="7602c-113">Desde el **archivo** menú, seleccione **agregar o quitar complemento**.</span><span class="sxs-lookup"><span data-stu-id="7602c-113">From the **File** menu, select **Add/Remove Snap In**.</span></span> 
    
    <span data-ttu-id="7602c-114">El **agregar o quitar complementos** aparecerá la ventana.</span><span class="sxs-lookup"><span data-stu-id="7602c-114">The **Add or Remove Snap-ins** window appears.</span></span>
  
3. <span data-ttu-id="7602c-115">Desde el **complementos disponibles** elija **certificados**, a continuación, seleccione **agregar**.</span><span class="sxs-lookup"><span data-stu-id="7602c-115">From the **Available snap-ins** list, choose **Certificates**, then select **Add**.</span></span>  

    ![Agregar complemento de certificado](./media/mmc-add-certificate-snap-in.png)
  
4. <span data-ttu-id="7602c-117">En el **complemento certificados** ventana, seleccione **cuenta de equipo**y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7602c-117">In the **Certificates snap-in** window, select **Computer account**, and then select **Next**.</span></span> 
  
    <span data-ttu-id="7602c-118">Si lo desea, puede seleccionar **mi cuenta de usuario** para el usuario actual o **cuenta de servicio** para un servicio determinado.</span><span class="sxs-lookup"><span data-stu-id="7602c-118">Optionally, you can select **My user account** for the current user or **Service account** for a particular service.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="7602c-119">Si no es un administrador para el dispositivo, puede administrar los certificados sólo para su cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="7602c-119">If you're not an administrator for your device, you can manage certificates only for your user account.</span></span>
  
5. <span data-ttu-id="7602c-120">En el **Seleccionar equipo** ventana, deje **ordenador** seleccionado y, a continuación, seleccione **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="7602c-120">In the **Select Computer** window, leave **Local computer** selected, and then select **Finish**.</span></span>  
  
6. <span data-ttu-id="7602c-121">En el **agregar o quitar complemento** ventana, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7602c-121">In the **Add or Remove Snap-in** window, select **OK**.</span></span>  
  
    ![Agregar complemento de certificado](./media/mmc-certificate-snap-in-selected.png)

7. <span data-ttu-id="7602c-123">Opcional: Desde el **archivo** menú, seleccione **guardar** o **Guardar como** para guardar el archivo de consola MMC para su uso posterior.</span><span class="sxs-lookup"><span data-stu-id="7602c-123">Optional: From the **File** menu, select **Save** or **Save As** to save the MMC console file for later use.</span></span>  

8. <span data-ttu-id="7602c-124">Para ver los certificados en el complemento de MMC, seleccione **raíz de consola** en el panel izquierdo, expanda **certificados (equipo Local)**.</span><span class="sxs-lookup"><span data-stu-id="7602c-124">To view your certificates in the MMC snap-in, select **Console Root** in the left pane, then expand **Certificates (Local Computer)**.</span></span>

    <span data-ttu-id="7602c-125">Aparece una lista de directorios para cada tipo de certificado.</span><span class="sxs-lookup"><span data-stu-id="7602c-125">A list of directories for each type of certificate appears.</span></span> <span data-ttu-id="7602c-126">En cada directorio de certificado, puede ver, exportar, importar y eliminar sus certificados.</span><span class="sxs-lookup"><span data-stu-id="7602c-126">From each certificate directory, you can view, export, import, and delete its certificates.</span></span>

## <a name="view-certificates-with-the-certificate-manager-tool"></a><span data-ttu-id="7602c-127">Ver certificados con la herramienta Administrador de certificados</span><span class="sxs-lookup"><span data-stu-id="7602c-127">View certificates with the Certificate Manager tool</span></span>

<span data-ttu-id="7602c-128">También puede ver, exportar, importar y eliminar certificados utilizando la herramienta Administrador de certificados.</span><span class="sxs-lookup"><span data-stu-id="7602c-128">You can also view, export, import, and delete certificates by using the Certificate Manager tool.</span></span>

### <a name="to-view-certificates-for-the-local-device"></a><span data-ttu-id="7602c-129">Para ver los certificados para el dispositivo local</span><span class="sxs-lookup"><span data-stu-id="7602c-129">To view certificates for the local device</span></span>

1. <span data-ttu-id="7602c-130">Seleccione **ejecutar** desde el **iniciar** menú y, a continuación, escriba *certlm.msc*.</span><span class="sxs-lookup"><span data-stu-id="7602c-130">Select **Run** from the **Start** menu, and then enter *certlm.msc*.</span></span> 

    <span data-ttu-id="7602c-131">Aparece la herramienta Administrador de certificados para el dispositivo local.</span><span class="sxs-lookup"><span data-stu-id="7602c-131">The Certificate Manager tool for the local device appears.</span></span> 
  
2. <span data-ttu-id="7602c-132">Para ver los certificados, en **certificados - equipo Local** en el panel izquierdo, expanda el directorio para el tipo de certificado que desea ver.</span><span class="sxs-lookup"><span data-stu-id="7602c-132">To view your certificates, under **Certificates - Local Computer** in the left pane, expand the directory for the type of certificate you want to view.</span></span>

### <a name="to-view-certificates-for-the-current-user"></a><span data-ttu-id="7602c-133">Para ver los certificados del usuario actual</span><span class="sxs-lookup"><span data-stu-id="7602c-133">To view certificates for the current user</span></span>

1. <span data-ttu-id="7602c-134">Seleccione **ejecutar** desde el **iniciar** menú y, a continuación, escriba *certmgr.msc*.</span><span class="sxs-lookup"><span data-stu-id="7602c-134">Select **Run** from the **Start** menu, and then enter *certmgr.msc*.</span></span> 

    <span data-ttu-id="7602c-135">Aparece la herramienta Administrador de certificados para el usuario actual.</span><span class="sxs-lookup"><span data-stu-id="7602c-135">The Certificate Manager tool for the current user appears.</span></span> 
  
2. <span data-ttu-id="7602c-136">Para ver los certificados, en **certificados - usuario actual** en el panel izquierdo, expanda el directorio para el tipo de certificado que desea ver.</span><span class="sxs-lookup"><span data-stu-id="7602c-136">To view your certificates, under **Certificates - Current User** in the left pane, expand the directory for the type of certificate you want to view.</span></span>

## <a name="see-also"></a><span data-ttu-id="7602c-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="7602c-137">See also</span></span>

- [<span data-ttu-id="7602c-138">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="7602c-138">Working with certificates</span></span>](working-with-certificates.md)
- [<span data-ttu-id="7602c-139">Cómo: Crear certificados temporales para su uso durante el desarrollo</span><span class="sxs-lookup"><span data-stu-id="7602c-139">How to: Create temporary certificates for use during development</span></span>](how-to-create-temporary-certificates-for-use-during-development.md)
- [<span data-ttu-id="7602c-140">Cómo: Recuperar la huella digital de un certificado</span><span class="sxs-lookup"><span data-stu-id="7602c-140">How to: Retrieve the thumbprint of a certificate</span></span>](how-to-retrieve-the-thumbprint-of-a-certificate.md)
