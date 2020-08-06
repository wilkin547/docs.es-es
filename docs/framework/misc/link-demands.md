---
title: Peticiones de vínculos
description: Lea acerca de las peticiones de vínculo, que producen una comprobación de seguridad durante la compilación Just-in-Time (JIT) y examine solo el ensamblado de llamada inmediato del código.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [.NET Framework], demands
- demanded permissions
- permissions [.NET Framework], demands
- granting permissions, demands
- code access security, demands
- user demands for permission
- caller security checks
- link demands
ms.assetid: a33fd5f9-2de9-4653-a4f0-d9df25082c4d
ms.openlocfilehash: 7f5475d5bfff8cc3c500f95b05d54daacc9b253e
ms.sourcegitcommit: c37e8d4642fef647ebab0e1c618ecc29ddfe2a0f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "87855795"
---
# <a name="link-demands"></a>Peticiones de vínculos

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 Una petición de vínculo hace que se produzca una comprobación de seguridad durante la compilación Just-In-Time y comprueba solo el ensamblado de llamada inmediato del código. La vinculación se produce cuando el código se enlaza a una referencia de tipo, incluidas las referencias del puntero de función y las llamadas a métodos. Si el ensamblado de llamada no tiene permisos suficientes para vincularse al código, no se permitirá el vínculo y se producirá una excepción en tiempo de ejecución cuando se cargue y ejecute el código. Las peticiones de vínculo pueden reemplazarse en las clases que heredan de su código.  
  
 No se realiza un recorrido de pila completo con este tipo de demanda y el código sigue siendo susceptible a ataques señuelo. Por ejemplo, si un método del ensamblado A está protegido por una petición de vínculo, se evalúa un llamador directo en el ensamblado B en función de los permisos del ensamblado B.  Sin embargo, la petición de vínculo no evaluará un método en el ensamblado C si llama indirectamente al método en el ensamblado A utilizando el método en el ensamblado B. La petición de vínculo especifica solo los permisos que los llamadores directos en el ensamblado de llamada inmediato deben tener para vincularse al código. No especifica los permisos que deben tener todos los llamadores para ejecutar el código.  
  
 Los modificadores de recorrido de pila <xref:System.Security.CodeAccessPermission.Assert%2A>, <xref:System.Security.CodeAccessPermission.Deny%2A> y <xref:System.Security.CodeAccessPermission.PermitOnly%2A> no afectan a la evaluación de las peticiones de vínculo.  Dado que las peticiones de vínculo no efectúan ningún recorrido de pila, los modificadores de recorrido de pila no tienen ningún efecto sobre las peticiones de vínculo.  
  
 Si se tiene acceso a un método protegido por una petición de vínculo a través de la [reflexión](../reflection-and-codedom/reflection.md), una petición de vínculo comprueba el llamador inmediato del código al que se tiene acceso mediante reflexión. Esto es válido tanto para la detección de métodos como para la invocación de métodos efectuados por reflexión. Por ejemplo, supongamos que el código usa la reflexión para devolver un <xref:System.Reflection.MethodInfo> objeto que representa un método protegido por una petición de vínculo y, a continuación, pasa ese objeto **MethodInfo** a otro código que usa el objeto para invocar el método original. En este caso, la comprobación de la petición de vínculo se produce dos veces: una vez para el código que devuelve el objeto **MethodInfo** y otra para el código que lo invoca.  
  
> [!NOTE]
> Una petición de vínculo efectuada en un constructor de clases estáticas no protege el constructor, puesto que el sistema llama a los constructores estáticos, fuera de la ruta de acceso de ejecución del código de la aplicación. Como resultado, al aplicar una petición de vínculo a toda una clase, no puede proteger el acceso a un constructor estático, aunque proteja el resto de la clase.  
  
 El siguiente fragmento de código especifica de manera declarativa que cualquier código vinculado al método `ReadData` debe tener el permiso `CustomPermission`. Este permiso es un permiso personalizado hipotético y no existe en .NET Framework. La petición se realiza pasando una marca **SecurityAction. LinkDemand** a `CustomPermissionAttribute` .  
  
```vb  
<CustomPermissionAttribute(SecurityAction.LinkDemand)> _  
Public Shared Function ReadData() As String  
    ' Access a custom resource.  
End Function
```  
  
```csharp  
[CustomPermissionAttribute(SecurityAction.LinkDemand)]  
public static string ReadData()  
{  
    // Access a custom resource.  
}  
```  
  
## <a name="see-also"></a>Vea también

- [Atributos](../../standard/attributes/index.md)
- [Seguridad de acceso del código](code-access-security.md)
