---
ms.openlocfilehash: 5c09bee92f679cd7e7a95cd23d5ce0ca9b57170c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614740"
---
### <a name="wcf-transport-security-supports-certificates-stored-using-cng"></a><span data-ttu-id="eef8d-101">La seguridad de transporte de WCF admite los certificados almacenados con CNG</span><span class="sxs-lookup"><span data-stu-id="eef8d-101">WCF transport security supports certificates stored using CNG</span></span>

#### <a name="details"></a><span data-ttu-id="eef8d-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="eef8d-102">Details</span></span>

<span data-ttu-id="eef8d-103">A partir de las aplicaciones destinadas a .NET Framework 4.6.2, la seguridad de transporte de WCF es compatible con los certificados almacenados mediante la biblioteca de criptografía (CNG) de Windows.</span><span class="sxs-lookup"><span data-stu-id="eef8d-103">Starting with apps that target the .NET Framework 4.6.2, WCF transport security supports certificates stored using the Windows Cryptography Library (CNG).</span></span> <span data-ttu-id="eef8d-104">Esta compatibilidad está limitada a los certificados con una clave pública que tengan un exponente con una longitud no superior a 32 bits.</span><span class="sxs-lookup"><span data-stu-id="eef8d-104">This support is limited to certificates with a public key that has an exponent no more than 32 bits in length.</span></span> <span data-ttu-id="eef8d-105">Cuando una aplicación está destinada a .NET Framework 4.6.2, esta característica está activada de manera predeterminada. En versiones anteriores de .NET Framework, el intento de usar certificados X509 con un proveedor de almacenamiento de claves CSG inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="eef8d-105">When an application targets the .NET Framework 4.6.2, this feature is on by default.In earlier versions of the .NET Framework, the attempt to use X509 certificates with a CSG key storage provider throws an exception.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="eef8d-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="eef8d-106">Suggestion</span></span>

<span data-ttu-id="eef8d-107">Las aplicaciones que tienen como destino .NET Framework 4.6.1 y versiones anteriores, pero que se ejecutan en .NET Framework 4.6.2, pueden habilitar la compatibilidad para los certificados de CNG si agregan la línea siguiente a la sección `<runtime>` del archivo app.config o web.config:</span><span class="sxs-lookup"><span data-stu-id="eef8d-107">Apps that target the .NET Framework 4.6.1 and earlier but are running on the .NET Framework 4.6.2 can enable support for CNG certificates by adding the following line to the `<runtime>` section of the app.config or web.config file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.ServiceModel.DisableCngCertificates=false" />
</runtime>
```

<span data-ttu-id="eef8d-108">Esto también puede realizarse mediante programación con el siguiente código:</span><span class="sxs-lookup"><span data-stu-id="eef8d-108">This can also be done programmatically with the following code:</span></span>

```csharp
private const string DisableCngCertificates = @"Switch.System.ServiceModel.DisableCngCertificate";

AppContext.SetSwitch(disableCngCertificates, false);
```

```vb
Const DisableCngCertificates As String = "Switch.System.ServiceModel.DisableCngCertificates"
AppContext.SetSwitch(disableCngCertificates, False)
```

<span data-ttu-id="eef8d-109">Tenga en cuenta que, debido a este cambio, cualquier código erróneo de control de excepciones que dependa del intento de iniciar una comunicación segura con un certificado CNG dejará de ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="eef8d-109">Note that, because of this change, any exception handling code that depends on the attempt to initiate secure communication with a CNG certificate to fail will no longer execute.</span></span>

| <span data-ttu-id="eef8d-110">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="eef8d-110">Name</span></span>    | <span data-ttu-id="eef8d-111">Valor</span><span class="sxs-lookup"><span data-stu-id="eef8d-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="eef8d-112">Ámbito</span><span class="sxs-lookup"><span data-stu-id="eef8d-112">Scope</span></span>   | <span data-ttu-id="eef8d-113">Secundaria</span><span class="sxs-lookup"><span data-stu-id="eef8d-113">Minor</span></span>       |
| <span data-ttu-id="eef8d-114">Versión</span><span class="sxs-lookup"><span data-stu-id="eef8d-114">Version</span></span> | <span data-ttu-id="eef8d-115">4.6.2</span><span class="sxs-lookup"><span data-stu-id="eef8d-115">4.6.2</span></span>       |
| <span data-ttu-id="eef8d-116">Tipo</span><span class="sxs-lookup"><span data-stu-id="eef8d-116">Type</span></span>    | <span data-ttu-id="eef8d-117">Redestinación</span><span class="sxs-lookup"><span data-stu-id="eef8d-117">Retargeting</span></span> |
