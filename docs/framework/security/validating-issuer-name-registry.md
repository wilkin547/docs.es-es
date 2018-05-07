---
title: Validar el Registro de nombres de emisores
ms.date: 03/30/2017
ms.assetid: c4644dd1-dead-48ff-abeb-7bffae69a6ac
ms.openlocfilehash: aa6a71ced0f9bf969eb6c8800739f629810dd63f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="validating-issuer-name-registry"></a>Validar el Registro de nombres de emisores
El registro de nombres de emisores de validación (VINR) de Windows Identity Foundation permite a las aplicaciones de varios inquilinos asegurarse de que un proveedor de identidad y un inquilino de confianza han emitido un token entrante. Esta funcionalidad es especialmente útil para las aplicaciones de varios inquilinos que usan Microsoft Azure Active Directory, ya que todos los tokens emitidos por Microsoft Azure AD se firman con el mismo certificado. Para diferenciar las solicitudes de varios inquilinos que usan el mismo certificado (y que, por tanto, tienen la misma huella digital), la aplicación debe conservar el nombre de emisor de cada inquilino para realizar la lógica de validación. El VINR proporciona esta funcionalidad y también permite agregar lógica de validación personalizada o almacenar los datos del Registro de emisores en ubicaciones distintas de un archivo de configuración. La extensión se puede agregar a la canalización WIF de la aplicación o usarse de forma independiente.  
  
 El VINR está disponible como paquete NuGet. Vea [Descargar el paquete de validación del Registro de nombres de emisores](../../../docs/framework/security/downloading-the-validating-issuer-name-registry-package.md) para obtener más información.  
  
## <a name="scenarios"></a>Escenarios  
 El VINR habilita el siguiente escenario clave:  
  
-   **Validar un token en una aplicación de varios inquilinos**: en este escenario, una empresa llamada Litware ha desarrollado una aplicación de varios inquilinos que usa un proveedor de identidad como Microsoft Azure AD. Esta aplicación tiene dos clientes: Contoso y Fabrikam. Cuando un usuario de Fabrikam se autentica en la aplicación de Litware, el token resultante de Microsoft Azure AD se firma mediante el certificado estándar y Fabrikam emite la solicitud. La aplicación debe comprobar que tanto el nombre del emisor como el token son válidos y debe diferenciar las solicitudes de Contoso firmadas con el mismo certificado de Microsoft Azure AD. El VINR facilita a la aplicación de Litware la distinción y validación de las solicitudes de varios inquilinos, como Contoso y Fabrikam.  
  
## <a name="features"></a>Características  
 El VINR ofrece las siguientes características:  
  
-   **Validación de nombre del emisor y token para las aplicaciones de varios inquilinos**: valida el token entrante comprobando el nombre del emisor (inquilino) y si el token se firmó mediante un certificado válido del proveedor de identidad.  
  
-   **Extensibilidad para la lógica de validación personalizada y los almacenes de datos**: proporciona extensibilidad para insertar su propia lógica de validación y especificar un almacén de datos distinto del archivo de configuración predeterminado.
