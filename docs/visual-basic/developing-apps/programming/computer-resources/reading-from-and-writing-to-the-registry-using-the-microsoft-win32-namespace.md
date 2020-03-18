---
title: Leer y escribir en el Registro mediante Microsoft.Win32 Namespace
ms.date: 07/20/2015
helpviewer_keywords:
- registry [Visual Basic]
ms.assetid: 4a0dcce0-c27b-4199-baa8-ee4528da6a56
ms.openlocfilehash: 841344186b8e56717b81e90397aabc608bdc6dab
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "74345496"
---
# <a name="reading-from-and-writing-to-the-registry-using-the-microsoftwin32-namespace-visual-basic"></a>Leer y escribir en el Registro mediante el espacio de nombres Microsoft.Win32 (Visual Basic)

Aunque `My.Computer.Registry` debería cubrir sus necesidades básicas al programar con el Registro, también puede usar las clases <xref:Microsoft.Win32.Registry> y <xref:Microsoft.Win32.RegistryKey> del espacio de nombres <xref:Microsoft.Win32> de .NET Framework.  
  
## <a name="keys-in-the-registry-class"></a>Claves de la clase Registry  

 La clase <xref:Microsoft.Win32.Registry> proporciona las claves base del Registro que se pueden usar para tener acceso a las subclaves y sus valores. Las claves base son de solo lectura. En la tabla siguiente se enumeran y se describen las siete claves expuestas por la clase <xref:Microsoft.Win32.Registry>.  
  
|**Key**|**Descripción**|  
|-------------|---------------------|  
|<xref:Microsoft.Win32.Registry.ClassesRoot>|Define los tipos de documentos y las propiedades asociadas con esos tipos.|  
|<xref:Microsoft.Win32.Registry.CurrentConfig>|Contiene información de configuración de hardware que no es específica del usuario.|  
|<xref:Microsoft.Win32.Registry.CurrentUser>|Contiene información sobre las preferencias del usuario actual, como las variables de entorno.|  
|<xref:Microsoft.Win32.Registry.DynData>|Contiene datos del Registro dinámicos, como los usados por los controladores de dispositivos virtuales.|  
|<xref:Microsoft.Win32.Registry.LocalMachine>|Contiene cinco subclaves (Hardware, SAM, Security, Software y System) que almacenan los datos de configuración del equipo local.|  
|<xref:Microsoft.Win32.Registry.PerformanceData>|Contiene información de rendimiento de los componentes de software.|  
|<xref:Microsoft.Win32.Registry.Users>|Contiene información sobre las preferencias del usuario predeterminado.|  
  
> [!IMPORTANT]
> Es más seguro escribir datos en el usuario actual (<xref:Microsoft.Win32.Registry.CurrentUser>) que en el equipo local (<xref:Microsoft.Win32.Registry.LocalMachine>). Cuando la clave que está creando fue creada anteriormente por otro proceso posiblemente malintencionado, se produce una condición normalmente conocida como "squatting". Para evitar que esto ocurra, use un método como <xref:Microsoft.Win32.RegistryKey.GetValue%2A>, que devuelve `Nothing` si la clave no existe.  
  
## <a name="reading-a-value-from-the-registry"></a>Leer un valor del Registro  

 En el código siguiente se muestra cómo leer una cadena de HKEY_CURRENT_USER.  
  
 [!code-vb[VbResourceTasks#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#20)]  
  
 En el código siguiente se lee, se incrementa y, después, se escribe una cadena en HKEY_CURRENT_USER.  
  
 [!code-vb[VbResourceTasks#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#21)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.SystemException>
- <xref:System.ApplicationException>
- <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>
- [Try...Catch...Finally (instrucción)](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [Leer y escribir en el Registro](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)
- [Seguridad y Registro](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md)
