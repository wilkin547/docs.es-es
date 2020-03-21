---
title: 'Cómo: Ver certificados con el complemento MMC'
ms.date: 02/25/2019
helpviewer_keywords:
- certificates [WCF], viewing with the MMC snap-in
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
ms.openlocfilehash: 35048c24e838c513909fae8bedcba287001f5cef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184780"
---
# <a name="how-to-view-certificates-with-the-mmc-snap-in"></a><span data-ttu-id="d4dbb-102">Cómo: Ver certificados con el complemento MMC</span><span class="sxs-lookup"><span data-stu-id="d4dbb-102">How to: View certificates with the MMC snap-in</span></span>
<span data-ttu-id="d4dbb-103">Al crear un cliente o servicio seguro, puede usar un [certificado](working-with-certificates.md) como credencial.</span><span class="sxs-lookup"><span data-stu-id="d4dbb-103">When you create a secure client or service, you can use a [certificate](working-with-certificates.md) as the credential.</span></span> <span data-ttu-id="d4dbb-104">Por ejemplo, un tipo común de credencial es el certificado X.509, que se crea con el <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="d4dbb-104">For example, a common type of credential is the X.509 certificate, which you create with the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="d4dbb-105">Hay tres tipos diferentes de almacenes de certificados que puede examinar con Microsoft Management Console (MMC) en sistemas Windows:</span><span class="sxs-lookup"><span data-stu-id="d4dbb-105">There are three different types of certificate stores that you can examine with the Microsoft Management Console (MMC) on Windows systems:</span></span>

- <span data-ttu-id="d4dbb-106">Equipo local: la tienda es local para el dispositivo y global para todos los usuarios del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d4dbb-106">Local computer: The store is local to the device and global to all users on the device.</span></span>

- <span data-ttu-id="d4dbb-107">Usuario actual: el almacén es local para la cuenta de usuario actual en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d4dbb-107">Current user: The store is local to the current user account on the device.</span></span>

- <span data-ttu-id="d4dbb-108">Cuenta de servicio: la tienda es local a un servicio determinado en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d4dbb-108">Service account: The store is local to a particular service on the device.</span></span>

## <a name="view-certificates-in-the-mmc-snap-in"></a><span data-ttu-id="d4dbb-109">Ver certificados en el complemento MMC</span><span class="sxs-lookup"><span data-stu-id="d4dbb-109">View certificates in the MMC snap-in</span></span>

<span data-ttu-id="d4dbb-110">El siguiente procedimiento muestra cómo examinar los almacenes del dispositivo local para encontrar un certificado adecuado:</span><span class="sxs-lookup"><span data-stu-id="d4dbb-110">The following procedure demonstrates how to examine the stores on your local device to find an appropriate certificate:</span></span>
  
1. <span data-ttu-id="d4dbb-111">Seleccione **Ejecutar en** el menú **Inicio** y, a continuación, escriba *mmc*.</span><span class="sxs-lookup"><span data-stu-id="d4dbb-111">Select **Run** from the **Start** menu, and then enter *mmc*.</span></span>

    <span data-ttu-id="d4dbb-112">Aparece el MMC.</span><span class="sxs-lookup"><span data-stu-id="d4dbb-112">The MMC appears.</span></span>
  
2. <span data-ttu-id="d4dbb-113">En el menú **Archivo,** seleccione **Agregar o quitar forzado de cursor**.</span><span class="sxs-lookup"><span data-stu-id="d4dbb-113">From the **File** menu, select **Add/Remove Snap In**.</span></span>

    <span data-ttu-id="d4dbb-114">Aparecerá la ventana **Agregar o quitar complementos.**</span><span class="sxs-lookup"><span data-stu-id="d4dbb-114">The **Add or Remove Snap-ins** window appears.</span></span>
  
3. <span data-ttu-id="d4dbb-115">En la lista **Complementos disponibles,** elija **Certificados**y, a continuación, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="d4dbb-115">From the **Available snap-ins** list, choose **Certificates**, then select **Add**.</span></span>  

    ![Agregar complemento de certificado](./media/mmc-add-certificate-snap-in.png)
  
4. <span data-ttu-id="d4dbb-117">En la ventana **Complemento Certificados,** seleccione **Cuenta de**equipo y, a continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="d4dbb-117">In the **Certificates snap-in** window, select **Computer account**, and then select **Next**.</span></span>
  
    <span data-ttu-id="d4dbb-118">Opcionalmente, puede seleccionar **Mi cuenta** de usuario para el usuario actual o la cuenta de **servicio** para un servicio determinado.</span><span class="sxs-lookup"><span data-stu-id="d4dbb-118">Optionally, you can select **My user account** for the current user or **Service account** for a particular service.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d4dbb-119">Si no eres administrador de tu dispositivo, puedes administrar certificados solo para tu cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="d4dbb-119">If you're not an administrator for your device, you can manage certificates only for your user account.</span></span>
  
5. <span data-ttu-id="d4dbb-120">En la ventana **Seleccionar equipo,** deje seleccionado **Equipo local** y, a continuación, seleccione **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="d4dbb-120">In the **Select Computer** window, leave **Local computer** selected, and then select **Finish**.</span></span>  
  
6. <span data-ttu-id="d4dbb-121">En la ventana **Agregar o quitar complemento,** seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d4dbb-121">In the **Add or Remove Snap-in** window, select **OK**.</span></span>  
  
    ![Agregar complemento de certificado](./media/mmc-certificate-snap-in-selected.png)

7. <span data-ttu-id="d4dbb-123">Opcional: en el menú **Archivo,** seleccione **Guardar** o **Guardar como** para guardar el archivo de consola de MMC para su uso posterior.</span><span class="sxs-lookup"><span data-stu-id="d4dbb-123">Optional: From the **File** menu, select **Save** or **Save As** to save the MMC console file for later use.</span></span>  

8. <span data-ttu-id="d4dbb-124">Para ver los certificados en el complemento MMC, seleccione Raíz de **consola** en el panel izquierdo y, a continuación, expanda **Certificados (equipo local).**</span><span class="sxs-lookup"><span data-stu-id="d4dbb-124">To view your certificates in the MMC snap-in, select **Console Root** in the left pane, then expand **Certificates (Local Computer)**.</span></span>

    <span data-ttu-id="d4dbb-125">Aparece una lista de directorios para cada tipo de certificado.</span><span class="sxs-lookup"><span data-stu-id="d4dbb-125">A list of directories for each type of certificate appears.</span></span> <span data-ttu-id="d4dbb-126">Desde cada directorio de certificados, puede ver, exportar, importar y eliminar sus certificados.</span><span class="sxs-lookup"><span data-stu-id="d4dbb-126">From each certificate directory, you can view, export, import, and delete its certificates.</span></span>

## <a name="view-certificates-with-the-certificate-manager-tool"></a><span data-ttu-id="d4dbb-127">Ver certificados con la herramienta Administrador de certificados</span><span class="sxs-lookup"><span data-stu-id="d4dbb-127">View certificates with the Certificate Manager tool</span></span>

<span data-ttu-id="d4dbb-128">También puede ver, exportar, importar y eliminar certificados mediante la herramienta Administrador de certificados.</span><span class="sxs-lookup"><span data-stu-id="d4dbb-128">You can also view, export, import, and delete certificates by using the Certificate Manager tool.</span></span>

### <a name="to-view-certificates-for-the-local-device"></a><span data-ttu-id="d4dbb-129">Para ver los certificados del dispositivo local</span><span class="sxs-lookup"><span data-stu-id="d4dbb-129">To view certificates for the local device</span></span>

1. <span data-ttu-id="d4dbb-130">Seleccione **Ejecutar en** el menú **Inicio** y, a continuación, escriba *certlm.msc*.</span><span class="sxs-lookup"><span data-stu-id="d4dbb-130">Select **Run** from the **Start** menu, and then enter *certlm.msc*.</span></span>

    <span data-ttu-id="d4dbb-131">Aparece la herramienta Administrador de certificados para el dispositivo local.</span><span class="sxs-lookup"><span data-stu-id="d4dbb-131">The Certificate Manager tool for the local device appears.</span></span>
  
2. <span data-ttu-id="d4dbb-132">Para ver los certificados, en **Certificados - Equipo local** en el panel izquierdo, expanda el directorio del tipo de certificado que desea ver.</span><span class="sxs-lookup"><span data-stu-id="d4dbb-132">To view your certificates, under **Certificates - Local Computer** in the left pane, expand the directory for the type of certificate you want to view.</span></span>

### <a name="to-view-certificates-for-the-current-user"></a><span data-ttu-id="d4dbb-133">Para ver los certificados del usuario actual</span><span class="sxs-lookup"><span data-stu-id="d4dbb-133">To view certificates for the current user</span></span>

1. <span data-ttu-id="d4dbb-134">Seleccione **Ejecutar en** el menú **Inicio** y, a continuación, escriba *certmgr.msc*.</span><span class="sxs-lookup"><span data-stu-id="d4dbb-134">Select **Run** from the **Start** menu, and then enter *certmgr.msc*.</span></span>

    <span data-ttu-id="d4dbb-135">Aparece la herramienta Administrador de certificados para el usuario actual.</span><span class="sxs-lookup"><span data-stu-id="d4dbb-135">The Certificate Manager tool for the current user appears.</span></span>
  
2. <span data-ttu-id="d4dbb-136">Para ver los certificados, en **Certificados - Usuario actual** en el panel izquierdo, expanda el directorio del tipo de certificado que desea ver.</span><span class="sxs-lookup"><span data-stu-id="d4dbb-136">To view your certificates, under **Certificates - Current User** in the left pane, expand the directory for the type of certificate you want to view.</span></span>

## <a name="see-also"></a><span data-ttu-id="d4dbb-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d4dbb-137">See also</span></span>

- [<span data-ttu-id="d4dbb-138">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="d4dbb-138">Working with certificates</span></span>](working-with-certificates.md)
- [<span data-ttu-id="d4dbb-139">Cómo: Crear certificados temporales para su uso durante el desarrollo</span><span class="sxs-lookup"><span data-stu-id="d4dbb-139">How to: Create temporary certificates for use during development</span></span>](how-to-create-temporary-certificates-for-use-during-development.md)
- [<span data-ttu-id="d4dbb-140">Cómo: Recuperar la huella digital de un certificado</span><span class="sxs-lookup"><span data-stu-id="d4dbb-140">How to: Retrieve the thumbprint of a certificate</span></span>](how-to-retrieve-the-thumbprint-of-a-certificate.md)
