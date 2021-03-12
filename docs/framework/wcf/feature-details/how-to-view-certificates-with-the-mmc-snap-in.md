---
title: 'Cómo: ver certificados con el complemento MMC'
description: Un cliente o servicio de WCF seguro puede usar un certificado como credencial. Obtenga información acerca de los tipos de almacenes de certificados que puede examinar mediante el complemento MMC.
ms.date: 02/25/2019
helpviewer_keywords:
- certificates [WCF], viewing with the MMC snap-in
ms.assetid: 2b8782aa-ebb4-4ee7-974b-90299e356dc5
ms.openlocfilehash: 788161db2e38dc942b0c638128f8599b0436c8fd
ms.sourcegitcommit: 46cfed35d79d70e08c313b9c664c7e76babab39e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2021
ms.locfileid: "102604585"
---
# <a name="how-to-view-certificates-with-the-mmc-snap-in"></a><span data-ttu-id="a1e22-104">Cómo: ver certificados con el complemento MMC</span><span class="sxs-lookup"><span data-stu-id="a1e22-104">How to: View certificates with the MMC snap-in</span></span>

<span data-ttu-id="a1e22-105">Al crear un cliente o servicio seguro, puede usar un [certificado](working-with-certificates.md) como credencial.</span><span class="sxs-lookup"><span data-stu-id="a1e22-105">When you create a secure client or service, you can use a [certificate](working-with-certificates.md) as the credential.</span></span> <span data-ttu-id="a1e22-106">Por ejemplo, un tipo común de credencial es el certificado X. 509, que se crea con el <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="a1e22-106">For example, a common type of credential is the X.509 certificate, which you create with the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="a1e22-107">Existen tres tipos diferentes de almacenes de certificados que se pueden examinar con Microsoft Management Console (MMC) en los sistemas de Windows:</span><span class="sxs-lookup"><span data-stu-id="a1e22-107">There are three different types of certificate stores that you can examine with the Microsoft Management Console (MMC) on Windows systems:</span></span>

- <span data-ttu-id="a1e22-108">Equipo local: el almacén es local para el dispositivo y es global para todos los usuarios del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a1e22-108">Local computer: The store is local to the device and global to all users on the device.</span></span>

- <span data-ttu-id="a1e22-109">Usuario actual: el almacén es local para la cuenta de usuario actual en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a1e22-109">Current user: The store is local to the current user account on the device.</span></span>

- <span data-ttu-id="a1e22-110">Cuenta de servicio: el almacén es local para un servicio determinado en el dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a1e22-110">Service account: The store is local to a particular service on the device.</span></span>

## <a name="view-certificates-in-the-mmc-snap-in"></a><span data-ttu-id="a1e22-111">Ver certificados en el complemento MMC</span><span class="sxs-lookup"><span data-stu-id="a1e22-111">View certificates in the MMC snap-in</span></span>

<span data-ttu-id="a1e22-112">El siguiente procedimiento muestra cómo examinar los almacenes en el dispositivo local para encontrar un certificado adecuado:</span><span class="sxs-lookup"><span data-stu-id="a1e22-112">The following procedure demonstrates how to examine the stores on your local device to find an appropriate certificate:</span></span>
  
1. <span data-ttu-id="a1e22-113">Seleccione **Ejecutar** en el menú **Inicio** y escriba *MMC*.</span><span class="sxs-lookup"><span data-stu-id="a1e22-113">Select **Run** from the **Start** menu, and then enter *mmc*.</span></span>

    <span data-ttu-id="a1e22-114">Aparece MMC.</span><span class="sxs-lookup"><span data-stu-id="a1e22-114">The MMC appears.</span></span>
  
2. <span data-ttu-id="a1e22-115">En el menú **archivo** , seleccione **Agregar o quitar complemento**.</span><span class="sxs-lookup"><span data-stu-id="a1e22-115">From the **File** menu, select **Add/Remove Snap In**.</span></span>

    <span data-ttu-id="a1e22-116">Aparece la ventana **Agregar o quitar complementos** .</span><span class="sxs-lookup"><span data-stu-id="a1e22-116">The **Add or Remove Snap-ins** window appears.</span></span>
  
3. <span data-ttu-id="a1e22-117">En la lista **complementos disponibles** , seleccione **certificados** y, a continuación, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="a1e22-117">From the **Available snap-ins** list, choose **Certificates**, then select **Add**.</span></span>  

    ![Agregar complemento de certificado](./media/mmc-add-certificate-snap-in.png)
  
4. <span data-ttu-id="a1e22-119">En la ventana del **complemento certificados** , seleccione **cuenta de equipo** y, a continuación, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="a1e22-119">In the **Certificates snap-in** window, select **Computer account**, and then select **Next**.</span></span>
  
    <span data-ttu-id="a1e22-120">Opcionalmente, puede seleccionar **mi cuenta de usuario** para el usuario actual o la **cuenta de servicio** para un servicio determinado.</span><span class="sxs-lookup"><span data-stu-id="a1e22-120">Optionally, you can select **My user account** for the current user or **Service account** for a particular service.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a1e22-121">Si no es administrador de su dispositivo, puede administrar certificados solo para su cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="a1e22-121">If you're not an administrator for your device, you can manage certificates only for your user account.</span></span>
  
5. <span data-ttu-id="a1e22-122">En la ventana **seleccionar equipo** , deje seleccionado **equipo local** y, a continuación, seleccione **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="a1e22-122">In the **Select Computer** window, leave **Local computer** selected, and then select **Finish**.</span></span>  
  
6. <span data-ttu-id="a1e22-123">En la ventana **Agregar o quitar complemento** , seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a1e22-123">In the **Add or Remove Snap-in** window, select **OK**.</span></span>  
  
    ![Agregar o quitar una ventana de complementos con el botón Aceptar resaltado](./media/mmc-certificate-snap-in-selected.png)

7. <span data-ttu-id="a1e22-125">Opcional: en el menú **archivo** , seleccione **Guardar** o **Guardar como** para guardar el archivo de consola MMC para su uso posterior.</span><span class="sxs-lookup"><span data-stu-id="a1e22-125">Optional: From the **File** menu, select **Save** or **Save As** to save the MMC console file for later use.</span></span>  

8. <span data-ttu-id="a1e22-126">Para ver los certificados en el complemento MMC, seleccione raíz de **consola** en el panel izquierdo y, a continuación, expanda **certificados (equipo local)**.</span><span class="sxs-lookup"><span data-stu-id="a1e22-126">To view your certificates in the MMC snap-in, select **Console Root** in the left pane, then expand **Certificates (Local Computer)**.</span></span>

    <span data-ttu-id="a1e22-127">Aparece una lista de directorios para cada tipo de certificado.</span><span class="sxs-lookup"><span data-stu-id="a1e22-127">A list of directories for each type of certificate appears.</span></span> <span data-ttu-id="a1e22-128">En cada directorio de certificados, puede ver, exportar, importar y eliminar sus certificados.</span><span class="sxs-lookup"><span data-stu-id="a1e22-128">From each certificate directory, you can view, export, import, and delete its certificates.</span></span>

## <a name="view-certificates-with-the-certificate-manager-tool"></a><span data-ttu-id="a1e22-129">Ver certificados con la herramienta Administrador de certificados</span><span class="sxs-lookup"><span data-stu-id="a1e22-129">View certificates with the Certificate Manager tool</span></span>

<span data-ttu-id="a1e22-130">También puede ver, exportar, importar y eliminar certificados mediante la herramienta Administrador de certificados.</span><span class="sxs-lookup"><span data-stu-id="a1e22-130">You can also view, export, import, and delete certificates by using the Certificate Manager tool.</span></span>

### <a name="to-view-certificates-for-the-local-device"></a><span data-ttu-id="a1e22-131">Para ver los certificados del dispositivo local</span><span class="sxs-lookup"><span data-stu-id="a1e22-131">To view certificates for the local device</span></span>

1. <span data-ttu-id="a1e22-132">Seleccione **Ejecutar** en el menú **Inicio** y, a continuación, escriba *certlm. msc*.</span><span class="sxs-lookup"><span data-stu-id="a1e22-132">Select **Run** from the **Start** menu, and then enter *certlm.msc*.</span></span>

    <span data-ttu-id="a1e22-133">Aparece la herramienta Administrador de certificados para el dispositivo local.</span><span class="sxs-lookup"><span data-stu-id="a1e22-133">The Certificate Manager tool for the local device appears.</span></span>
  
2. <span data-ttu-id="a1e22-134">Para ver los certificados, en **certificados: equipo local** en el panel izquierdo, expanda el directorio del tipo de certificado que desea ver.</span><span class="sxs-lookup"><span data-stu-id="a1e22-134">To view your certificates, under **Certificates - Local Computer** in the left pane, expand the directory for the type of certificate you want to view.</span></span>

### <a name="to-view-certificates-for-the-current-user"></a><span data-ttu-id="a1e22-135">Para ver los certificados del usuario actual</span><span class="sxs-lookup"><span data-stu-id="a1e22-135">To view certificates for the current user</span></span>

1. <span data-ttu-id="a1e22-136">Seleccione **Ejecutar** en el menú **Inicio** y, a continuación, escriba *certmgr.msc*.</span><span class="sxs-lookup"><span data-stu-id="a1e22-136">Select **Run** from the **Start** menu, and then enter *certmgr.msc*.</span></span>

    <span data-ttu-id="a1e22-137">Aparece la herramienta Administrador de certificados para el usuario actual.</span><span class="sxs-lookup"><span data-stu-id="a1e22-137">The Certificate Manager tool for the current user appears.</span></span>
  
2. <span data-ttu-id="a1e22-138">Para ver los certificados, en **certificados: usuario actual** en el panel izquierdo, expanda el directorio del tipo de certificado que desea ver.</span><span class="sxs-lookup"><span data-stu-id="a1e22-138">To view your certificates, under **Certificates - Current User** in the left pane, expand the directory for the type of certificate you want to view.</span></span>

## <a name="see-also"></a><span data-ttu-id="a1e22-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1e22-139">See also</span></span>

- [<span data-ttu-id="a1e22-140">Trabajar con certificados</span><span class="sxs-lookup"><span data-stu-id="a1e22-140">Working with certificates</span></span>](working-with-certificates.md)
- [<span data-ttu-id="a1e22-141">Cómo: crear certificados temporales para su uso durante el desarrollo</span><span class="sxs-lookup"><span data-stu-id="a1e22-141">How to: Create temporary certificates for use during development</span></span>](how-to-create-temporary-certificates-for-use-during-development.md)
- [<span data-ttu-id="a1e22-142">Cómo: recuperar la huella digital de un certificado</span><span class="sxs-lookup"><span data-stu-id="a1e22-142">How to: Retrieve the thumbprint of a certificate</span></span>](how-to-retrieve-the-thumbprint-of-a-certificate.md)
