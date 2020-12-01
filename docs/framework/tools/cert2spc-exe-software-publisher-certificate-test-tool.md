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
ms.openlocfilehash: 0bcc785a51f2ca46195970130178d0cfa705ee6e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96247328"
---
# <a name="cert2spcexe-software-publisher-certificate-test-tool"></a><span data-ttu-id="f9f2a-104">Cert2spc.exe (Herramienta de prueba de certificados del publicador de software)</span><span class="sxs-lookup"><span data-stu-id="f9f2a-104">Cert2spc.exe (Software Publisher Certificate Test Tool)</span></span>

<span data-ttu-id="f9f2a-105">La herramienta de prueba de certificados de editor de software crea un certificado de editor de software (SPC) a partir de uno o varios certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="f9f2a-105">The Software Publisher Certificate Test tool creates a Software Publisher's Certificate (SPC) from one or more X.509 certificates.</span></span> <span data-ttu-id="f9f2a-106">Cert2spc.exe se utiliza únicamente para pruebas.</span><span class="sxs-lookup"><span data-stu-id="f9f2a-106">Cert2spc.exe is for test purposes only.</span></span> <span data-ttu-id="f9f2a-107">Se puede obtener un certificado SPC válido de una entidad de certificación como VeriSign o Thawte.</span><span class="sxs-lookup"><span data-stu-id="f9f2a-107">You can obtain a valid SPC from a Certification Authority such as VeriSign or Thawte.</span></span> <span data-ttu-id="f9f2a-108">Para más información sobre cómo crear certificados X.509, consulte [Makecert.exe (Herramienta de creación de certificados)](/windows/desktop/SecCrypto/makecert).</span><span class="sxs-lookup"><span data-stu-id="f9f2a-108">For more information about creating X.509 certificates, see [Makecert.exe (Certificate Creation Tool)](/windows/desktop/SecCrypto/makecert).</span></span>  
  
 <span data-ttu-id="f9f2a-109">Esta herramienta se instala automáticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f9f2a-109">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="f9f2a-110">Para ejecutar la herramienta, use Símbolo del sistema para desarrolladores de Visual Studio (o Símbolo del sistema de Visual Studio en Windows 7).</span><span class="sxs-lookup"><span data-stu-id="f9f2a-110">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="f9f2a-111">Para más información, consulte [Símbolos del sistema](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="f9f2a-111">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="f9f2a-112">En el símbolo del sistema, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f9f2a-112">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9f2a-113">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f9f2a-113">Syntax</span></span>  
  
```console  
cert2spc cert1.cer | crl1.crl [... certN.cer | crlN.crl] outputSPCfile.spc  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9f2a-114">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f9f2a-114">Parameters</span></span>  
  
|<span data-ttu-id="f9f2a-115">Argumento</span><span class="sxs-lookup"><span data-stu-id="f9f2a-115">Argument</span></span>|<span data-ttu-id="f9f2a-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="f9f2a-116">Description</span></span>|  
|--------------|-----------------|  
|`certN.cer`|<span data-ttu-id="f9f2a-117">Nombre de certificado X.509 que se incluye en el archivo SPC.</span><span class="sxs-lookup"><span data-stu-id="f9f2a-117">The name of an X.509 certificate to include in the SPC file.</span></span> <span data-ttu-id="f9f2a-118">Se pueden especificar varios nombres separados por espacios.</span><span class="sxs-lookup"><span data-stu-id="f9f2a-118">You can specify multiple names separated by spaces.</span></span>|  
|`crlN.crl`|<span data-ttu-id="f9f2a-119">Nombre de la lista de revocación de certificados que se va a incluir en el archivo SPC.</span><span class="sxs-lookup"><span data-stu-id="f9f2a-119">The name of a certificate revocation list to include in the SPC file.</span></span> <span data-ttu-id="f9f2a-120">Se pueden especificar varios nombres separados por espacios.</span><span class="sxs-lookup"><span data-stu-id="f9f2a-120">You can specify multiple names separated by spaces.</span></span>|  
|`outputSPCfile.spc`|<span data-ttu-id="f9f2a-121">Nombre del objeto PKCS #7 que contendrá los certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="f9f2a-121">The name of the PKCS #7 object that will contain the X.509 certificates.</span></span>|  
  
|<span data-ttu-id="f9f2a-122">Opción</span><span class="sxs-lookup"><span data-stu-id="f9f2a-122">Option</span></span>|<span data-ttu-id="f9f2a-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="f9f2a-123">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="f9f2a-124">**/?**</span><span class="sxs-lookup"><span data-stu-id="f9f2a-124">**/?**</span></span>|<span data-ttu-id="f9f2a-125">Muestra las opciones y la sintaxis de los comandos para la herramienta.</span><span class="sxs-lookup"><span data-stu-id="f9f2a-125">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="examples"></a><span data-ttu-id="f9f2a-126">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="f9f2a-126">Examples</span></span>  

 <span data-ttu-id="f9f2a-127">El comando siguiente crea un SPC a partir de `myCertificate.cer` y lo coloca en `mySPCFile.spc`.</span><span class="sxs-lookup"><span data-stu-id="f9f2a-127">The following command creates an SPC from `myCertificate.cer` and places it in `mySPCFile.spc`.</span></span>  
  
```console
cert2spc myCertificate.cer mySPCFile.spc  
```  
  
 <span data-ttu-id="f9f2a-128">El comando siguiente crea un SPC a partir de `oneCertificate.cer` y `twoCertificate.cer` y lo coloca en `mySPCFile.spc`.</span><span class="sxs-lookup"><span data-stu-id="f9f2a-128">The following command creates an SPC from `oneCertificate.cer` and `twoCertificate.cer`, and places it in `mySPCFile.spc`.</span></span>  
  
```console
cert2spc oneCertificate.cer twoCertificate.cer mySPCFile.spc  
```  
  
## <a name="see-also"></a><span data-ttu-id="f9f2a-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9f2a-129">See also</span></span>

- [<span data-ttu-id="f9f2a-130">Herramientas</span><span class="sxs-lookup"><span data-stu-id="f9f2a-130">Tools</span></span>](index.md)
- [<span data-ttu-id="f9f2a-131">Makecert.exe (Herramienta de creación de certificados)</span><span class="sxs-lookup"><span data-stu-id="f9f2a-131">Makecert.exe (Certificate Creation Tool)</span></span>](/windows/desktop/SecCrypto/makecert)
- [<span data-ttu-id="f9f2a-132">Símbolos del sistema</span><span class="sxs-lookup"><span data-stu-id="f9f2a-132">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
