---
title: Cert2spc.exe (Herramienta de prueba de certificados del publicador de software)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- SPC
- Software Publisher Certificate Test tool
- Software Publisher Certificate
- Cert2spc.exe
- certificates, Software Publisher's Certificate
ms.assetid: be434d7d-9c0d-46e7-8392-58a9b542d11d
caps.latest.revision: 21
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 7109f96b6997670afa6ef7c362b9e1a142014fbe
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="cert2spcexe-software-publisher-certificate-test-tool"></a><span data-ttu-id="965b5-102">Cert2spc.exe (Herramienta de prueba de certificados del publicador de software)</span><span class="sxs-lookup"><span data-stu-id="965b5-102">Cert2spc.exe (Software Publisher Certificate Test Tool)</span></span>
<span data-ttu-id="965b5-103">La herramienta de prueba de certificados de editor de software crea un certificado de editor de software (SPC) a partir de uno o varios certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="965b5-103">The Software Publisher Certificate Test tool creates a Software Publisher's Certificate (SPC) from one or more X.509 certificates.</span></span> <span data-ttu-id="965b5-104">Cert2spc.exe se utiliza únicamente para pruebas.</span><span class="sxs-lookup"><span data-stu-id="965b5-104">Cert2spc.exe is for test purposes only.</span></span> <span data-ttu-id="965b5-105">Se puede obtener un certificado SPC válido de una entidad de certificación como VeriSign o Thawte.</span><span class="sxs-lookup"><span data-stu-id="965b5-105">You can obtain a valid SPC from a Certification Authority such as VeriSign or Thawte.</span></span> <span data-ttu-id="965b5-106">Para más información sobre cómo crear certificados X.509, consulte [Makecert.exe (Herramienta de creación de certificados)](http://msdn.microsoft.com/library/b0343f8e-9c41-4852-a85c-f8a0c408cf0d).</span><span class="sxs-lookup"><span data-stu-id="965b5-106">For more information about creating X.509 certificates, see [Makecert.exe (Certificate Creation Tool)](http://msdn.microsoft.com/library/b0343f8e-9c41-4852-a85c-f8a0c408cf0d).</span></span>  
  
 <span data-ttu-id="965b5-107">Esta herramienta se instala automáticamente con Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="965b5-107">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="965b5-108">Para ejecutar la herramienta, utilice el Símbolo del sistema para desarrolladores (o el Símbolo del sistema de Visual Studio en Windows 7).</span><span class="sxs-lookup"><span data-stu-id="965b5-108">To run the tool, use the Developer Command Prompt (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="965b5-109">Para más información, consulte [Símbolos del sistema](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="965b5-109">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="965b5-110">En el símbolo del sistema, escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="965b5-110">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="965b5-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="965b5-111">Syntax</span></span>  
  
```  
cert2spc cert1.cer | crl1.crl [... certN.cer | crlN.crl] outputSPCfile.spc  
```  
  
#### <a name="parameters"></a><span data-ttu-id="965b5-112">Parámetros</span><span class="sxs-lookup"><span data-stu-id="965b5-112">Parameters</span></span>  
  
|<span data-ttu-id="965b5-113">Argumento</span><span class="sxs-lookup"><span data-stu-id="965b5-113">Argument</span></span>|<span data-ttu-id="965b5-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="965b5-114">Description</span></span>|  
|--------------|-----------------|  
|`certN.cer`|<span data-ttu-id="965b5-115">Nombre de certificado X.509 que se incluye en el archivo SPC.</span><span class="sxs-lookup"><span data-stu-id="965b5-115">The name of an X.509 certificate to include in the SPC file.</span></span> <span data-ttu-id="965b5-116">Se pueden especificar varios nombres separados por espacios.</span><span class="sxs-lookup"><span data-stu-id="965b5-116">You can specify multiple names separated by spaces.</span></span>|  
|`crlN.crl`|<span data-ttu-id="965b5-117">Nombre de la lista de revocación de certificados que se va a incluir en el archivo SPC.</span><span class="sxs-lookup"><span data-stu-id="965b5-117">The name of a certificate revocation list to include in the SPC file.</span></span> <span data-ttu-id="965b5-118">Se pueden especificar varios nombres separados por espacios.</span><span class="sxs-lookup"><span data-stu-id="965b5-118">You can specify multiple names separated by spaces.</span></span>|  
|`outputSPCfile.spc`|<span data-ttu-id="965b5-119">Nombre del objeto PKCS #7 que contendrá los certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="965b5-119">The name of the PKCS #7 object that will contain the X.509 certificates.</span></span>|  
  
|<span data-ttu-id="965b5-120">Opción</span><span class="sxs-lookup"><span data-stu-id="965b5-120">Option</span></span>|<span data-ttu-id="965b5-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="965b5-121">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="965b5-122">**/?**</span><span class="sxs-lookup"><span data-stu-id="965b5-122">**/?**</span></span>|<span data-ttu-id="965b5-123">Muestra las opciones y la sintaxis de los comandos para la herramienta.</span><span class="sxs-lookup"><span data-stu-id="965b5-123">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="examples"></a><span data-ttu-id="965b5-124">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="965b5-124">Examples</span></span>  
 <span data-ttu-id="965b5-125">El comando siguiente crea un SPC a partir de `myCertificate.cer` y lo coloca en `mySPCFile.spc`.</span><span class="sxs-lookup"><span data-stu-id="965b5-125">The following command creates an SPC from `myCertificate.cer` and places it in `mySPCFile.spc`.</span></span>  
  
```  
cert2spc myCertificate.cer mySPCFile.spc  
```  
  
 <span data-ttu-id="965b5-126">El comando siguiente crea un SPC a partir de `oneCertificate.cer` y `twoCertificate.cer` y lo coloca en `mySPCFile.spc`.</span><span class="sxs-lookup"><span data-stu-id="965b5-126">The following command creates an SPC from `oneCertificate.cer` and `twoCertificate.cer`, and places it in `mySPCFile.spc`.</span></span>  
  
```  
cert2spc oneCertificate.cer twoCertificate.cer mySPCFile.spc  
```  
  
## <a name="see-also"></a><span data-ttu-id="965b5-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="965b5-127">See Also</span></span>  
 <span data-ttu-id="965b5-128">[Herramientas](../../../docs/framework/tools/index.md) </span><span class="sxs-lookup"><span data-stu-id="965b5-128">[Tools](../../../docs/framework/tools/index.md) </span></span>  
 <span data-ttu-id="965b5-129">[Makecert.exe (herramienta de creación de certificados)](http://msdn.microsoft.com/library/b0343f8e-9c41-4852-a85c-f8a0c408cf0d) </span><span class="sxs-lookup"><span data-stu-id="965b5-129">[Makecert.exe (Certificate Creation Tool)](http://msdn.microsoft.com/library/b0343f8e-9c41-4852-a85c-f8a0c408cf0d) </span></span>  
 [<span data-ttu-id="965b5-130">Símbolos del sistema</span><span class="sxs-lookup"><span data-stu-id="965b5-130">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)

