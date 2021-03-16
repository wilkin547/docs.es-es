---
title: Cert2spc.exe (Herramienta de prueba de certificados del publicador de software)
description: Use Cert2spc.exe, la herramienta de prueba de certificados del publicador de software. Esta herramienta crea un certificado de publicador de software (SPC) a partir de uno o varios certificados X.509.
ms.date: 03/30/2017
helpviewer_keywords:
- SPC
- Software Publisher Certificate Test tool
- Software Publisher Certificate
- Cert2spc.exe
- certificates, Software Publisher's Certificate
ms.assetid: be434d7d-9c0d-46e7-8392-58a9b542d11d
ms.openlocfilehash: 96b4c05f6c9af6fc78aa55b248a88de84e2d4ac8
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102258290"
---
# <a name="cert2spcexe-software-publisher-certificate-test-tool"></a><span data-ttu-id="408a4-104">Cert2spc.exe (Herramienta de prueba de certificados del publicador de software)</span><span class="sxs-lookup"><span data-stu-id="408a4-104">Cert2spc.exe (Software Publisher Certificate Test Tool)</span></span>

<span data-ttu-id="408a4-105">La herramienta de prueba de certificados de editor de software crea un certificado de editor de software (SPC) a partir de uno o varios certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="408a4-105">The Software Publisher Certificate Test tool creates a Software Publisher's Certificate (SPC) from one or more X.509 certificates.</span></span> <span data-ttu-id="408a4-106">Cert2spc.exe se utiliza únicamente para pruebas.</span><span class="sxs-lookup"><span data-stu-id="408a4-106">Cert2spc.exe is for test purposes only.</span></span> <span data-ttu-id="408a4-107">Se puede obtener un certificado SPC válido de una entidad de certificación como VeriSign o Thawte.</span><span class="sxs-lookup"><span data-stu-id="408a4-107">You can obtain a valid SPC from a Certification Authority such as VeriSign or Thawte.</span></span> <span data-ttu-id="408a4-108">Para más información sobre cómo crear certificados X.509, consulte [Makecert.exe (Herramienta de creación de certificados)](/windows/desktop/SecCrypto/makecert).</span><span class="sxs-lookup"><span data-stu-id="408a4-108">For more information about creating X.509 certificates, see [Makecert.exe (Certificate Creation Tool)](/windows/desktop/SecCrypto/makecert).</span></span>  
  
 <span data-ttu-id="408a4-109">Esta herramienta se instala automáticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="408a4-109">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="408a4-110">Para ejecutar la herramienta, use un [shell de línea de comandos para desarrolladores](/visualstudio/ide/reference/command-prompt-powershell).</span><span class="sxs-lookup"><span data-stu-id="408a4-110">To run the tool, use a [command-line shell for developers](/visualstudio/ide/reference/command-prompt-powershell).</span></span>  
  
 <span data-ttu-id="408a4-111">En el símbolo del sistema, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="408a4-111">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="408a4-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="408a4-112">Syntax</span></span>  
  
```console  
cert2spc cert1.cer | crl1.crl [... certN.cer | crlN.crl] outputSPCfile.spc  
```  
  
## <a name="parameters"></a><span data-ttu-id="408a4-113">Parámetros</span><span class="sxs-lookup"><span data-stu-id="408a4-113">Parameters</span></span>  
  
|<span data-ttu-id="408a4-114">Argumento</span><span class="sxs-lookup"><span data-stu-id="408a4-114">Argument</span></span>|<span data-ttu-id="408a4-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="408a4-115">Description</span></span>|  
|--------------|-----------------|  
|`certN.cer`|<span data-ttu-id="408a4-116">Nombre de certificado X.509 que se incluye en el archivo SPC.</span><span class="sxs-lookup"><span data-stu-id="408a4-116">The name of an X.509 certificate to include in the SPC file.</span></span> <span data-ttu-id="408a4-117">Se pueden especificar varios nombres separados por espacios.</span><span class="sxs-lookup"><span data-stu-id="408a4-117">You can specify multiple names separated by spaces.</span></span>|  
|`crlN.crl`|<span data-ttu-id="408a4-118">Nombre de la lista de revocación de certificados que se va a incluir en el archivo SPC.</span><span class="sxs-lookup"><span data-stu-id="408a4-118">The name of a certificate revocation list to include in the SPC file.</span></span> <span data-ttu-id="408a4-119">Se pueden especificar varios nombres separados por espacios.</span><span class="sxs-lookup"><span data-stu-id="408a4-119">You can specify multiple names separated by spaces.</span></span>|  
|`outputSPCfile.spc`|<span data-ttu-id="408a4-120">Nombre del objeto PKCS #7 que contendrá los certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="408a4-120">The name of the PKCS #7 object that will contain the X.509 certificates.</span></span>|  
  
|<span data-ttu-id="408a4-121">Opción</span><span class="sxs-lookup"><span data-stu-id="408a4-121">Option</span></span>|<span data-ttu-id="408a4-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="408a4-122">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="408a4-123">**/?**</span><span class="sxs-lookup"><span data-stu-id="408a4-123">**/?**</span></span>|<span data-ttu-id="408a4-124">Muestra las opciones y la sintaxis de los comandos para la herramienta.</span><span class="sxs-lookup"><span data-stu-id="408a4-124">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="examples"></a><span data-ttu-id="408a4-125">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="408a4-125">Examples</span></span>  

 <span data-ttu-id="408a4-126">El comando siguiente crea un SPC a partir de `myCertificate.cer` y lo coloca en `mySPCFile.spc`.</span><span class="sxs-lookup"><span data-stu-id="408a4-126">The following command creates an SPC from `myCertificate.cer` and places it in `mySPCFile.spc`.</span></span>  
  
```console
cert2spc myCertificate.cer mySPCFile.spc  
```  
  
 <span data-ttu-id="408a4-127">El comando siguiente crea un SPC a partir de `oneCertificate.cer` y `twoCertificate.cer` y lo coloca en `mySPCFile.spc`.</span><span class="sxs-lookup"><span data-stu-id="408a4-127">The following command creates an SPC from `oneCertificate.cer` and `twoCertificate.cer`, and places it in `mySPCFile.spc`.</span></span>  
  
```console
cert2spc oneCertificate.cer twoCertificate.cer mySPCFile.spc  
```  
  
## <a name="see-also"></a><span data-ttu-id="408a4-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="408a4-128">See also</span></span>

- [<span data-ttu-id="408a4-129">Herramientas</span><span class="sxs-lookup"><span data-stu-id="408a4-129">Tools</span></span>](index.md)
- [<span data-ttu-id="408a4-130">Makecert.exe (Herramienta de creación de certificados)</span><span class="sxs-lookup"><span data-stu-id="408a4-130">Makecert.exe (Certificate Creation Tool)</span></span>](/windows/desktop/SecCrypto/makecert)
- [<span data-ttu-id="408a4-131">Shells de línea de comandos para desarrolladores</span><span class="sxs-lookup"><span data-stu-id="408a4-131">Developer command-line shells</span></span>](/visualstudio/ide/reference/command-prompt-powershell)
