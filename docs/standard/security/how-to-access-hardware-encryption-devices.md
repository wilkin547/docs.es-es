---
title: Procedimiento para obtener acceso a los dispositivos de cifrado de hardware
ms.date: 07/14/2020
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
ms.openlocfilehash: c4f0b77985dea1818729af41b69a4a7d30427415
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829900"
---
# <a name="how-to-access-hardware-encryption-devices"></a><span data-ttu-id="8bbce-102">Procedimiento para obtener acceso a los dispositivos de cifrado de hardware</span><span class="sxs-lookup"><span data-stu-id="8bbce-102">How to: Access Hardware Encryption Devices</span></span>

> [!NOTE]
> <span data-ttu-id="8bbce-103">Este artículo se aplica a Windows.</span><span class="sxs-lookup"><span data-stu-id="8bbce-103">This article applies to Windows.</span></span>

<span data-ttu-id="8bbce-104">Puede usar la clase <xref:System.Security.Cryptography.CspParameters> para obtener acceso a los dispositivos de cifrado de hardware.</span><span class="sxs-lookup"><span data-stu-id="8bbce-104">You can use the <xref:System.Security.Cryptography.CspParameters> class to access hardware encryption devices.</span></span> <span data-ttu-id="8bbce-105">Por ejemplo, puede usar esta clase para integrar la aplicación con una tarjeta inteligente, un generador de números aleatorios de hardware o una implementación de hardware de un determinado algoritmo criptográfico.</span><span class="sxs-lookup"><span data-stu-id="8bbce-105">For example, you can use this class to integrate your application with a smart card, a hardware random number generator, or a hardware implementation of a particular cryptographic algorithm.</span></span>  

<span data-ttu-id="8bbce-106">La clase <xref:System.Security.Cryptography.CspParameters> crea un proveedor de servicios criptográficos (CSP) que tiene acceso a un dispositivo de cifrado de hardware correctamente instalado.</span><span class="sxs-lookup"><span data-stu-id="8bbce-106">The <xref:System.Security.Cryptography.CspParameters> class creates a cryptographic service provider (CSP) that accesses a properly installed hardware encryption device.</span></span>  <span data-ttu-id="8bbce-107">Puede comprobar la disponibilidad de un CSP inspeccionando la siguiente clave del registro con el Editor del registro (Regedit.exe): HKEY_LOCAL_MACHINE\Software\Microsoft\Cryptography\Defaults\Provider.</span><span class="sxs-lookup"><span data-stu-id="8bbce-107">You can verify the availability of a CSP by inspecting the following registry key using the Registry Editor (Regedit.exe):  HKEY_LOCAL_MACHINE\Software\Microsoft\Cryptography\Defaults\Provider.</span></span>  
  
### <a name="to-sign-data-using-a-key-card"></a><span data-ttu-id="8bbce-108">Para firmar datos mediante una tarjeta de claves</span><span class="sxs-lookup"><span data-stu-id="8bbce-108">To sign data using a key card</span></span>  
  
1. <span data-ttu-id="8bbce-109">Cree una instancia nueva de la clase <xref:System.Security.Cryptography.CspParameters>; para ello, pase el tipo de proveedor entero y el nombre del proveedor al constructor.</span><span class="sxs-lookup"><span data-stu-id="8bbce-109">Create a new instance of the <xref:System.Security.Cryptography.CspParameters> class, passing the integer provider type and the provider name to the constructor.</span></span>  
  
2. <span data-ttu-id="8bbce-110">Pase las marcas adecuadas a la propiedad <xref:System.Security.Cryptography.CspParameters.Flags%2A> del objeto <xref:System.Security.Cryptography.CspParameters> recién creado.</span><span class="sxs-lookup"><span data-stu-id="8bbce-110">Pass the appropriate flags to the <xref:System.Security.Cryptography.CspParameters.Flags%2A> property of the newly created <xref:System.Security.Cryptography.CspParameters> object.</span></span>  <span data-ttu-id="8bbce-111">Por ejemplo, pase la marca <xref:System.Security.Cryptography.CspProviderFlags.UseDefaultKeyContainer>.</span><span class="sxs-lookup"><span data-stu-id="8bbce-111">For example, pass the <xref:System.Security.Cryptography.CspProviderFlags.UseDefaultKeyContainer> flag.</span></span>  
  
3. <span data-ttu-id="8bbce-112">Cree una nueva instancia de una clase <xref:System.Security.Cryptography.AsymmetricAlgorithm> (por ejemplo, la clase <xref:System.Security.Cryptography.RSACryptoServiceProvider>) pasando el objeto <xref:System.Security.Cryptography.CspParameters> al constructor.</span><span class="sxs-lookup"><span data-stu-id="8bbce-112">Create a new instance of an <xref:System.Security.Cryptography.AsymmetricAlgorithm> class (for example, the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class), passing the <xref:System.Security.Cryptography.CspParameters> object to the constructor.</span></span>  
  
4. <span data-ttu-id="8bbce-113">Firme los datos mediante uno de los métodos `Sign` y compruebe los datos mediante uno de los métodos `Verify`.</span><span class="sxs-lookup"><span data-stu-id="8bbce-113">Sign your data using one of the `Sign` methods and verify your data using one of the `Verify` methods.</span></span>  
  
### <a name="to-generate-a-random-number-using-a-hardware-random-number-generator"></a><span data-ttu-id="8bbce-114">Para generar un número aleatorio mediante un generador de números aleatorios de hardware</span><span class="sxs-lookup"><span data-stu-id="8bbce-114">To generate a random number using a hardware random number generator</span></span>  
  
1. <span data-ttu-id="8bbce-115">Cree una instancia nueva de la clase <xref:System.Security.Cryptography.CspParameters>; para ello, pase el tipo de proveedor entero y el nombre del proveedor al constructor.</span><span class="sxs-lookup"><span data-stu-id="8bbce-115">Create a new instance of the <xref:System.Security.Cryptography.CspParameters> class, passing the integer provider type and the provider name to the constructor.</span></span>  
  
2. <span data-ttu-id="8bbce-116">Cree una nueva instancia del <xref:System.Security.Cryptography.RNGCryptoServiceProvider> pasando el objeto <xref:System.Security.Cryptography.CspParameters> al constructor.</span><span class="sxs-lookup"><span data-stu-id="8bbce-116">Create a new instance of the <xref:System.Security.Cryptography.RNGCryptoServiceProvider>, passing the <xref:System.Security.Cryptography.CspParameters> object to the constructor.</span></span>  
  
3. <span data-ttu-id="8bbce-117">Cree un valor aleatorio con el método <xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetBytes%2A> o <xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetNonZeroBytes%2A>.</span><span class="sxs-lookup"><span data-stu-id="8bbce-117">Create a random value using the <xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetBytes%2A> or <xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetNonZeroBytes%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8bbce-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8bbce-118">Example</span></span>

<span data-ttu-id="8bbce-119">En el siguiente ejemplo de código se muestra cómo firmar datos con una tarjeta inteligente.</span><span class="sxs-lookup"><span data-stu-id="8bbce-119">The following code example demonstrates how to sign data using a smart card.</span></span>  <span data-ttu-id="8bbce-120">El ejemplo de código crea un objeto <xref:System.Security.Cryptography.CspParameters> que expone una tarjeta inteligente e inicializa un objeto <xref:System.Security.Cryptography.RSACryptoServiceProvider> con el CSP.</span><span class="sxs-lookup"><span data-stu-id="8bbce-120">The code example creates a <xref:System.Security.Cryptography.CspParameters> object that exposes a smart card, and then initializes an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object using the CSP.</span></span>  <span data-ttu-id="8bbce-121">Después, el ejemplo de código firma y comprueba algunos datos.</span><span class="sxs-lookup"><span data-stu-id="8bbce-121">The code example then signs and verifies some data.</span></span>  

<span data-ttu-id="8bbce-122">Debido a problemas de colisión con SHA1, se recomienda SHA256 o superior.</span><span class="sxs-lookup"><span data-stu-id="8bbce-122">Due to collision problems with SHA1, we recommend SHA256 or better.</span></span>
  
[!code-cpp[Cryptography.SmartCardCSP#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Cryptography.SmartCardCSP/CPP/Cryptography.SmartCardCSP.cpp#1)]
[!code-csharp[Cryptography.SmartCardCSP#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Cryptography.SmartCardCSP/CS/example.cs#1)]
[!code-vb[Cryptography.SmartCardCSP#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Cryptography.SmartCardCSP/VB/example.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8bbce-123">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="8bbce-123">Compiling the Code</span></span>  
  
- <span data-ttu-id="8bbce-124">Incluya los espacios de nombres <xref:System> y <xref:System.Security.Cryptography>.</span><span class="sxs-lookup"><span data-stu-id="8bbce-124">Include the <xref:System> and <xref:System.Security.Cryptography> namespaces.</span></span>  
  
- <span data-ttu-id="8bbce-125">Debe tener un lector de tarjetas inteligentes y los controladores correspondientes instalados en el equipo.</span><span class="sxs-lookup"><span data-stu-id="8bbce-125">You must have a smart card reader and drivers installed on your computer.</span></span>  
  
- <span data-ttu-id="8bbce-126">Debe inicializar el objeto <xref:System.Security.Cryptography.CspParameters> con la información específica de su lector de tarjetas.</span><span class="sxs-lookup"><span data-stu-id="8bbce-126">You must initialize the <xref:System.Security.Cryptography.CspParameters> object using information specific to your card reader.</span></span>  <span data-ttu-id="8bbce-127">Para obtener más información, consulte la documentación de su lector de tarjetas.</span><span class="sxs-lookup"><span data-stu-id="8bbce-127">For more information, see the documentation of your card reader.</span></span>

## <a name="see-also"></a><span data-ttu-id="8bbce-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="8bbce-128">See also</span></span>

- [<span data-ttu-id="8bbce-129">Modelo de criptografía</span><span class="sxs-lookup"><span data-stu-id="8bbce-129">Cryptography Model</span></span>](cryptography-model.md)
- [<span data-ttu-id="8bbce-130">servicios criptográficos</span><span class="sxs-lookup"><span data-stu-id="8bbce-130">Cryptographic Services</span></span>](cryptographic-services.md)
- [<span data-ttu-id="8bbce-131">Criptografía multiplataforma</span><span class="sxs-lookup"><span data-stu-id="8bbce-131">Cross-Platform Cryptography</span></span>](cross-platform-cryptography.md)
- [<span data-ttu-id="8bbce-132">ASP.NET Core protección de datos</span><span class="sxs-lookup"><span data-stu-id="8bbce-132">ASP.NET Core Data Protection</span></span>](/aspnet/core/security/data-protection/introduction)
