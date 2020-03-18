---
title: Cert2spc.exe (Herramienta de prueba de certificados del publicador de software)
ms.date: 03/30/2017
helpviewer_keywords:
- SPC
- Software Publisher Certificate Test tool
- Software Publisher Certificate
- Cert2spc.exe
- certificates, Software Publisher's Certificate
ms.assetid: be434d7d-9c0d-46e7-8392-58a9b542d11d
ms.openlocfilehash: 809b7d0383f172a5fbcb2ac4ac3ffb96ff0b8e20
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "73129886"
---
# <a name="cert2spcexe-software-publisher-certificate-test-tool"></a><span data-ttu-id="28792-102">Cert2spc.exe (Herramienta de prueba de certificados del publicador de software)</span><span class="sxs-lookup"><span data-stu-id="28792-102">Cert2spc.exe (Software Publisher Certificate Test Tool)</span></span>
<span data-ttu-id="28792-103">La herramienta de prueba de certificados de editor de software crea un certificado de editor de software (SPC) a partir de uno o varios certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="28792-103">The Software Publisher Certificate Test tool creates a Software Publisher's Certificate (SPC) from one or more X.509 certificates.</span></span> <span data-ttu-id="28792-104">Cert2spc.exe se utiliza únicamente para pruebas.</span><span class="sxs-lookup"><span data-stu-id="28792-104">Cert2spc.exe is for test purposes only.</span></span> <span data-ttu-id="28792-105">Se puede obtener un certificado SPC válido de una entidad de certificación como VeriSign o Thawte.</span><span class="sxs-lookup"><span data-stu-id="28792-105">You can obtain a valid SPC from a Certification Authority such as VeriSign or Thawte.</span></span> <span data-ttu-id="28792-106">Para más información sobre cómo crear certificados X.509, consulte [Makecert.exe (Herramienta de creación de certificados)](/windows/desktop/SecCrypto/makecert).</span><span class="sxs-lookup"><span data-stu-id="28792-106">For more information about creating X.509 certificates, see [Makecert.exe (Certificate Creation Tool)](/windows/desktop/SecCrypto/makecert).</span></span>  
  
 <span data-ttu-id="28792-107">Esta herramienta se instala automáticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="28792-107">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="28792-108">Para ejecutar la herramienta, use Símbolo del sistema para desarrolladores de Visual Studio (o Símbolo del sistema de Visual Studio en Windows 7).</span><span class="sxs-lookup"><span data-stu-id="28792-108">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="28792-109">Para más información, consulte [Símbolos del sistema](developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="28792-109">For more information, see [Command Prompts](developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="28792-110">En el símbolo del sistema, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="28792-110">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28792-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="28792-111">Syntax</span></span>  
  
```console  
cert2spc cert1.cer | crl1.crl [... certN.cer | crlN.crl] outputSPCfile.spc  
```  
  
## <a name="parameters"></a><span data-ttu-id="28792-112">Parámetros</span><span class="sxs-lookup"><span data-stu-id="28792-112">Parameters</span></span>  
  
|<span data-ttu-id="28792-113">Argumento</span><span class="sxs-lookup"><span data-stu-id="28792-113">Argument</span></span>|<span data-ttu-id="28792-114">Description</span><span class="sxs-lookup"><span data-stu-id="28792-114">Description</span></span>|  
|--------------|-----------------|  
|`certN.cer`|<span data-ttu-id="28792-115">Nombre de certificado X.509 que se incluye en el archivo SPC.</span><span class="sxs-lookup"><span data-stu-id="28792-115">The name of an X.509 certificate to include in the SPC file.</span></span> <span data-ttu-id="28792-116">Se pueden especificar varios nombres separados por espacios.</span><span class="sxs-lookup"><span data-stu-id="28792-116">You can specify multiple names separated by spaces.</span></span>|  
|`crlN.crl`|<span data-ttu-id="28792-117">Nombre de la lista de revocación de certificados que se va a incluir en el archivo SPC.</span><span class="sxs-lookup"><span data-stu-id="28792-117">The name of a certificate revocation list to include in the SPC file.</span></span> <span data-ttu-id="28792-118">Se pueden especificar varios nombres separados por espacios.</span><span class="sxs-lookup"><span data-stu-id="28792-118">You can specify multiple names separated by spaces.</span></span>|  
|`outputSPCfile.spc`|<span data-ttu-id="28792-119">Nombre del objeto PKCS #7 que contendrá los certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="28792-119">The name of the PKCS #7 object that will contain the X.509 certificates.</span></span>|  
  
|<span data-ttu-id="28792-120">Opción</span><span class="sxs-lookup"><span data-stu-id="28792-120">Option</span></span>|<span data-ttu-id="28792-121">Description</span><span class="sxs-lookup"><span data-stu-id="28792-121">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="28792-122">**/?**</span><span class="sxs-lookup"><span data-stu-id="28792-122">**/?**</span></span>|<span data-ttu-id="28792-123">Muestra las opciones y la sintaxis de los comandos para la herramienta.</span><span class="sxs-lookup"><span data-stu-id="28792-123">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="examples"></a><span data-ttu-id="28792-124">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="28792-124">Examples</span></span>  
 <span data-ttu-id="28792-125">El comando siguiente crea un SPC a partir de `myCertificate.cer` y lo coloca en `mySPCFile.spc`.</span><span class="sxs-lookup"><span data-stu-id="28792-125">The following command creates an SPC from `myCertificate.cer` and places it in `mySPCFile.spc`.</span></span>  
  
```console
cert2spc myCertificate.cer mySPCFile.spc  
```  
  
 <span data-ttu-id="28792-126">El comando siguiente crea un SPC a partir de `oneCertificate.cer` y `twoCertificate.cer` y lo coloca en `mySPCFile.spc`.</span><span class="sxs-lookup"><span data-stu-id="28792-126">The following command creates an SPC from `oneCertificate.cer` and `twoCertificate.cer`, and places it in `mySPCFile.spc`.</span></span>  
  
```console
cert2spc oneCertificate.cer twoCertificate.cer mySPCFile.spc  
```  
  
## <a name="see-also"></a><span data-ttu-id="28792-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="28792-127">See also</span></span>

- [<span data-ttu-id="28792-128">Herramientas</span><span class="sxs-lookup"><span data-stu-id="28792-128">Tools</span></span>](index.md)
- [<span data-ttu-id="28792-129">Makecert.exe (Herramienta de creación de certificados)</span><span class="sxs-lookup"><span data-stu-id="28792-129">Makecert.exe (Certificate Creation Tool)</span></span>](/windows/desktop/SecCrypto/makecert)
- [<span data-ttu-id="28792-130">Símbolos del sistema</span><span class="sxs-lookup"><span data-stu-id="28792-130">Command Prompts</span></span>](developer-command-prompt-for-vs.md)
