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
# <a name="how-to-access-hardware-encryption-devices"></a>Procedimiento para obtener acceso a los dispositivos de cifrado de hardware

> [!NOTE]
> Este artículo se aplica a Windows.

Puede usar la clase <xref:System.Security.Cryptography.CspParameters> para obtener acceso a los dispositivos de cifrado de hardware. Por ejemplo, puede usar esta clase para integrar la aplicación con una tarjeta inteligente, un generador de números aleatorios de hardware o una implementación de hardware de un determinado algoritmo criptográfico.  

La clase <xref:System.Security.Cryptography.CspParameters> crea un proveedor de servicios criptográficos (CSP) que tiene acceso a un dispositivo de cifrado de hardware correctamente instalado.  Puede comprobar la disponibilidad de un CSP inspeccionando la siguiente clave del registro con el Editor del registro (Regedit.exe): HKEY_LOCAL_MACHINE\Software\Microsoft\Cryptography\Defaults\Provider.  
  
### <a name="to-sign-data-using-a-key-card"></a>Para firmar datos mediante una tarjeta de claves  
  
1. Cree una instancia nueva de la clase <xref:System.Security.Cryptography.CspParameters>; para ello, pase el tipo de proveedor entero y el nombre del proveedor al constructor.  
  
2. Pase las marcas adecuadas a la propiedad <xref:System.Security.Cryptography.CspParameters.Flags%2A> del objeto <xref:System.Security.Cryptography.CspParameters> recién creado.  Por ejemplo, pase la marca <xref:System.Security.Cryptography.CspProviderFlags.UseDefaultKeyContainer>.  
  
3. Cree una nueva instancia de una clase <xref:System.Security.Cryptography.AsymmetricAlgorithm> (por ejemplo, la clase <xref:System.Security.Cryptography.RSACryptoServiceProvider>) pasando el objeto <xref:System.Security.Cryptography.CspParameters> al constructor.  
  
4. Firme los datos mediante uno de los métodos `Sign` y compruebe los datos mediante uno de los métodos `Verify`.  
  
### <a name="to-generate-a-random-number-using-a-hardware-random-number-generator"></a>Para generar un número aleatorio mediante un generador de números aleatorios de hardware  
  
1. Cree una instancia nueva de la clase <xref:System.Security.Cryptography.CspParameters>; para ello, pase el tipo de proveedor entero y el nombre del proveedor al constructor.  
  
2. Cree una nueva instancia del <xref:System.Security.Cryptography.RNGCryptoServiceProvider> pasando el objeto <xref:System.Security.Cryptography.CspParameters> al constructor.  
  
3. Cree un valor aleatorio con el método <xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetBytes%2A> o <xref:System.Security.Cryptography.RNGCryptoServiceProvider.GetNonZeroBytes%2A>.  
  
## <a name="example"></a>Ejemplo

En el siguiente ejemplo de código se muestra cómo firmar datos con una tarjeta inteligente.  El ejemplo de código crea un objeto <xref:System.Security.Cryptography.CspParameters> que expone una tarjeta inteligente e inicializa un objeto <xref:System.Security.Cryptography.RSACryptoServiceProvider> con el CSP.  Después, el ejemplo de código firma y comprueba algunos datos.  

Debido a problemas de colisión con SHA1, se recomienda SHA256 o superior.
  
[!code-cpp[Cryptography.SmartCardCSP#1](../../../samples/snippets/cpp/VS_Snippets_CLR/Cryptography.SmartCardCSP/CPP/Cryptography.SmartCardCSP.cpp#1)]
[!code-csharp[Cryptography.SmartCardCSP#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Cryptography.SmartCardCSP/CS/example.cs#1)]
[!code-vb[Cryptography.SmartCardCSP#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Cryptography.SmartCardCSP/VB/example.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
  
- Incluya los espacios de nombres <xref:System> y <xref:System.Security.Cryptography>.  
  
- Debe tener un lector de tarjetas inteligentes y los controladores correspondientes instalados en el equipo.  
  
- Debe inicializar el objeto <xref:System.Security.Cryptography.CspParameters> con la información específica de su lector de tarjetas.  Para obtener más información, consulte la documentación de su lector de tarjetas.

## <a name="see-also"></a>Vea también

- [Modelo de criptografía](cryptography-model.md)
- [servicios criptográficos](cryptographic-services.md)
- [Criptografía multiplataforma](cross-platform-cryptography.md)
- [ASP.NET Core protección de datos](/aspnet/core/security/data-protection/introduction)
