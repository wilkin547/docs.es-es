---
title: Procedimiento para obtener acceso a los dispositivos de cifrado de hardware
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- encryption
- key card
- cryptography
- hardware encryption
- CspParameters
ms.assetid: b0e734df-6eb4-4b16-b48c-6f0fe82d5f17
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 33af618ac3971df76683fd64346e1aa1e5977177
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61795207"
---
# <a name="how-to-access-hardware-encryption-devices"></a><span data-ttu-id="53759-102">Procedimiento para obtener acceso a los dispositivos de cifrado de hardware</span><span class="sxs-lookup"><span data-stu-id="53759-102">How to: Access Hardware Encryption Devices</span></span>
<span data-ttu-id="53759-103">Puede usar la clase <xref:System.Security.Cryptography.CspParameters> para obtener acceso a los dispositivos de cifrado de hardware.</span><span class="sxs-lookup"><span data-stu-id="53759-103">You can use the <xref:System.Security.Cryptography.CspParameters> class to access hardware encryption devices.</span></span> <span data-ttu-id="53759-104">Por ejemplo, puede usar esta clase para integrar la aplicación con una tarjeta inteligente, un generador de números aleatorios de hardware o una implementación de hardware de un determinado algoritmo criptográfico.</span><span class="sxs-lookup"><span data-stu-id="53759-104">For example, you can use this class to integrate your application with a smart card, a hardware random number generator, or a hardware implementation of a particular cryptographic algorithm.</span></span>  
  
 <span data-ttu-id="53759-105">La clase <xref:System.Security.Cryptography.CspParameters> crea un proveedor de servicios criptográficos (CSP) que tiene acceso a un dispositivo de cifrado de hardware correctamente instalado.</span><span class="sxs-lookup"><span data-stu-id="53759-105">The <xref:System.Security.Cryptography.CspParameters> class creates a cryptographic service provider (CSP) that accesses a properly installed hardware encryption device.</span></span>  <span data-ttu-id="53759-106">Puede comprobar la disponibilidad de un CSP inspeccionando la siguiente clave del registro mediante el Editor del registro (Regedit.exe):  HKEY_LOCAL_MACHINE\Software\Microsoft\Cryptography\Defaults\Provider.</span><span class="sxs-lookup"><span data-stu-id="53759-106">You can verify the availability of a CSP by inspecting the following registry key using the Registry Editor (Regedit.exe):  HKEY_LOCAL_MACHINE\Software\Microsoft\Cryptography\Defaults\Provider.</span></span>  
  
### <a name="to-sign-data-using-a-key-card"></a><span data-ttu-id="53759-107">Para firmar datos mediante una tarjeta de claves</span><span class="sxs-lookup"><span data-stu-id="53759-107">To sign data using a key card</span></span>  
  
1. <span data-ttu-id="53759-108">Cree una instancia nueva de la clase <xref:System.Security.Cryptography.CspParameters>; para ello, pase el tipo de proveedor entero y el nombre del proveedor al constructor.</span><span class="sxs-lookup"><span data-stu-id="53759-108">Create a new instance of the <xref:System.Security.Cryptography.CspParameters> class, passing the integer provider type and the provider name to the constructor.</span></span>  
  
2. <span data-ttu-id="53759-109">Pase las marcas adecuadas a la propiedad <xref:System.Security.Cryptography.CspParameters.Flags%2A> del objeto <xref:System.Security.Cryptography.CspParameters> recién creado.</span><span class="sxs-lookup"><span data-stu-id="53759-109">Pass the appropriate flags to the <xref:System.Security.Cryptography.CspParameters.Flags%2A> property of the newly created <xref:System.Security.Cryptography.CspParameters> object.</span></span>  <span data-ttu-id="53759-110">Por ejemplo, pase la marca <xref:System.Security.Cryptography.CspProviderFlags.UseDefaultKeyContainer>.</span><span class="sxs-lookup"><span data-stu-id="53759-110">For example, pass the <xref:System.Security.Cryptography.CspProviderFlags.UseDefaultKeyContainer> flag.</span></span>  
  
3. <span data-ttu-id="53759-111">Cree una nueva instancia de una clase <xref:System.Security.Cryptography.AsymmetricAlgorithm> (por ejemplo, la clase <xref:System.Security.Cryptography.RSACryptoServiceProvider>) pasando el objeto <xref:System.Security.Cryptography.CspParameters> al constructor.</span><span class="sxs-lookup"><span data-stu-id="53759-111">Create a new instance of an <xref:System.Security.Cryptography.AsymmetricAlgorithm> class (for example, the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class), passing the <xref:System.Security.Cryptography.CspParameters> object to the constructor.</span></span>  
  
4. <span data-ttu-id="53759-112">Firme los datos mediante uno de los métodos `Sign` y compruebe los datos mediante uno de los métodos `Verify`.</span><span class="sxs-lookup"><span data-stu-id="53759-112">Sign your data using one of the `Sign` methods and verify your data using one of the `Verify` methods.</span></span>  
  
### <a name="to-generate-a-random-number-using-a-hardware-random-number-generator"></a><span data-ttu-id="53759-113">Para generar un número aleatorio mediante un generador de números aleatorios de hardware</span><span class="sxs-lookup"><span data-stu-id="53759-113">To generate a random number using a hardware random number generator</span></span>  
  
1. <span data-ttu-id="53759-114">Cree una instancia nueva de la clase <xref:System.Security.Cryptography.CspParameters>; para ello, pase el tipo de proveedor entero y el nombre del proveedor al constructor.</span><span class="sxs-lookup"><span data-stu-id="53759-114">Create a new instance of the <xref:System.Security.Cryptography.CspParameters> class, passing the integer provider type and the provider name to the constructor.</span></span>  
  
2. <span data-ttu-id="53759-115">Cree una nueva instancia del <xref:System.Security.Cryptography.RNGCryptoServiceProvider> pasando el objeto <xref:System.Security.Cryptography.CspParameters> al constructor.</span><span class="sxs-lookup"><span data-stu-id="53759-115">Create a new instance of the <xref:System.Security.Cryptography.RNGCryptoServiceProvider>, passing the <xref:System.Security.Cryptography.CspParameters> object to the constructor.</span></span>  
  
3. <span data-ttu-id="53759-116">Cree un valor aleatorio con el método <xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetBytes%2A> o <xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetNonZeroBytes%2A>.</span><span class="sxs-lookup"><span data-stu-id="53759-116">Create a random value using the <xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetBytes%2A> or <xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetNonZeroBytes%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="53759-117">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="53759-117">Example</span></span>  
 <span data-ttu-id="53759-118">En el siguiente ejemplo de código se muestra cómo firmar datos con una tarjeta inteligente.</span><span class="sxs-lookup"><span data-stu-id="53759-118">The following code example demonstrates how to sign data using a smart card.</span></span>  <span data-ttu-id="53759-119">El ejemplo de código crea un objeto <xref:System.Security.Cryptography.CspParameters> que expone una tarjeta inteligente e inicializa un objeto <xref:System.Security.Cryptography.RSACryptoServiceProvider> con el CSP.</span><span class="sxs-lookup"><span data-stu-id="53759-119">The code example creates a <xref:System.Security.Cryptography.CspParameters> object that exposes a smart card, and then initializes an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object using the CSP.</span></span>  <span data-ttu-id="53759-120">Después, el ejemplo de código firma y comprueba algunos datos.</span><span class="sxs-lookup"><span data-stu-id="53759-120">The code example then signs and verifies some data.</span></span>  
  
 [!code-cpp[Cryptography.SmartCardCSP#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Cryptography.SmartCardCSP/CPP/Cryptography.SmartCardCSP.cpp#1)]
 [!code-csharp[Cryptography.SmartCardCSP#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Cryptography.SmartCardCSP/CS/example.cs#1)]
 [!code-vb[Cryptography.SmartCardCSP#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Cryptography.SmartCardCSP/VB/example.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="53759-121">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="53759-121">Compiling the Code</span></span>  
  
- <span data-ttu-id="53759-122">Incluya los espacios de nombres <xref:System> y <xref:System.Security.Cryptography>.</span><span class="sxs-lookup"><span data-stu-id="53759-122">Include the <xref:System> and <xref:System.Security.Cryptography> namespaces.</span></span>  
  
- <span data-ttu-id="53759-123">Debe tener un lector de tarjetas inteligentes y los controladores correspondientes instalados en el equipo.</span><span class="sxs-lookup"><span data-stu-id="53759-123">You must have a smart card reader and drivers installed on your computer.</span></span>  
  
- <span data-ttu-id="53759-124">Debe inicializar el objeto <xref:System.Security.Cryptography.CspParameters> con la información específica de su lector de tarjetas.</span><span class="sxs-lookup"><span data-stu-id="53759-124">You must initialize the <xref:System.Security.Cryptography.CspParameters> object using information specific to your card reader.</span></span>  <span data-ttu-id="53759-125">Para obtener más información, consulte la documentación de su lector de tarjetas.</span><span class="sxs-lookup"><span data-stu-id="53759-125">For more information, see the documentation of your card reader.</span></span>
