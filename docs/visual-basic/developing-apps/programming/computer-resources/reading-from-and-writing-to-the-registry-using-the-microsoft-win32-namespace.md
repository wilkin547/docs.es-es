---
title: Leer y escribir en el Registro mediante el espacio de nombres Microsoft.Win32 (Visual Basic)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- registry, Visual Basic
ms.assetid: 4a0dcce0-c27b-4199-baa8-ee4528da6a56
caps.latest.revision: 20
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: cefde5317b2ed2bc0a2834224b1475e8020f7f25
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="reading-from-and-writing-to-the-registry-using-the-microsoftwin32-namespace-visual-basic"></a><span data-ttu-id="5b09e-102">Leer y escribir en el Registro mediante el espacio de nombres Microsoft.Win32 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5b09e-102">Reading from and Writing to the Registry Using the Microsoft.Win32 Namespace (Visual Basic)</span></span>
<span data-ttu-id="5b09e-103">Aunque `My.Computer.Registry` debería cubrir sus necesidades básicas al programar con el Registro, también puede usar las clases <xref:Microsoft.Win32.Registry> y <xref:Microsoft.Win32.RegistryKey> en el espacio de nombres <xref:Microsoft.Win32> de [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b09e-103">Although `My.Computer.Registry` should cover your basic needs when programming against the registry, you can also use the <xref:Microsoft.Win32.Registry> and <xref:Microsoft.Win32.RegistryKey> classes in the <xref:Microsoft.Win32> namespace of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)].</span></span>  
  
## <a name="keys-in-the-registry-class"></a><span data-ttu-id="5b09e-104">Claves de la clase Registry</span><span class="sxs-lookup"><span data-stu-id="5b09e-104">Keys in the Registry Class</span></span>  
 <span data-ttu-id="5b09e-105">La clase <xref:Microsoft.Win32.Registry> proporciona las claves base del Registro que se pueden usar para tener acceso a las subclaves y sus valores.</span><span class="sxs-lookup"><span data-stu-id="5b09e-105">The <xref:Microsoft.Win32.Registry> class supplies the base registry keys that can be used to access subkeys and their values.</span></span> <span data-ttu-id="5b09e-106">Las claves base son de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="5b09e-106">The base keys themselves are read-only.</span></span> <span data-ttu-id="5b09e-107">En la tabla siguiente se enumeran y se describen las siete claves expuestas por la clase <xref:Microsoft.Win32.Registry>.</span><span class="sxs-lookup"><span data-stu-id="5b09e-107">The following table lists and describes the seven keys exposed by the <xref:Microsoft.Win32.Registry> class.</span></span>  
  
|<span data-ttu-id="5b09e-108">**Key**</span><span class="sxs-lookup"><span data-stu-id="5b09e-108">**Key**</span></span>|<span data-ttu-id="5b09e-109">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="5b09e-109">**Description**</span></span>|  
|-------------|---------------------|  
|<xref:Microsoft.Win32.Registry.ClassesRoot>|<span data-ttu-id="5b09e-110">Define los tipos de documentos y las propiedades asociadas con esos tipos.</span><span class="sxs-lookup"><span data-stu-id="5b09e-110">Defines the types of documents and the properties associated with those types.</span></span>|  
|<xref:Microsoft.Win32.Registry.CurrentConfig>|<span data-ttu-id="5b09e-111">Contiene información de configuración de hardware que no es específica del usuario.</span><span class="sxs-lookup"><span data-stu-id="5b09e-111">Contains hardware configuration information that is not user-specific.</span></span>|  
|<xref:Microsoft.Win32.Registry.CurrentUser>|<span data-ttu-id="5b09e-112">Contiene información sobre las preferencias del usuario actual, como las variables de entorno.</span><span class="sxs-lookup"><span data-stu-id="5b09e-112">Contains information about the current user preferences, such as environmental variables.</span></span>|  
|<xref:Microsoft.Win32.Registry.DynData>|<span data-ttu-id="5b09e-113">Contiene datos del Registro dinámicos, como los usados por los controladores de dispositivos virtuales.</span><span class="sxs-lookup"><span data-stu-id="5b09e-113">Contains dynamic registry data, such as that used by Virtual Device Drivers.</span></span>|  
|<xref:Microsoft.Win32.Registry.LocalMachine>|<span data-ttu-id="5b09e-114">Contiene cinco subclaves (Hardware, SAM, Security, Software y System) que almacenan los datos de configuración del equipo local.</span><span class="sxs-lookup"><span data-stu-id="5b09e-114">Contains five subkeys (Hardware, SAM, Security, Software, and System) that hold the configuration data for the local computer.</span></span>|  
|<xref:Microsoft.Win32.Registry.PerformanceData>|<span data-ttu-id="5b09e-115">Contiene información de rendimiento de los componentes de software.</span><span class="sxs-lookup"><span data-stu-id="5b09e-115">Contains performance information for software components.</span></span>|  
|<xref:Microsoft.Win32.Registry.Users>|<span data-ttu-id="5b09e-116">Contiene información sobre las preferencias del usuario predeterminado.</span><span class="sxs-lookup"><span data-stu-id="5b09e-116">Contains information about the default user preferences.</span></span>|  
  
> [!IMPORTANT]
>  <span data-ttu-id="5b09e-117">Es más seguro escribir datos en el usuario actual (<xref:Microsoft.Win32.Registry.CurrentUser>) que en el equipo local (<xref:Microsoft.Win32.Registry.LocalMachine>).</span><span class="sxs-lookup"><span data-stu-id="5b09e-117">It is more secure to write data to the current user (<xref:Microsoft.Win32.Registry.CurrentUser>) than to the local computer (<xref:Microsoft.Win32.Registry.LocalMachine>).</span></span> <span data-ttu-id="5b09e-118">Cuando la clave que está creando fue creada anteriormente por otro proceso posiblemente malintencionado, se produce una condición normalmente conocida como "squatting".</span><span class="sxs-lookup"><span data-stu-id="5b09e-118">A condition that's typically referred to as "squatting" occurs when the key you are creating was previously created by another, possibly malicious, process.</span></span> <span data-ttu-id="5b09e-119">Para evitar que esto ocurra, use un método como <xref:Microsoft.Win32.RegistryKey.GetValue%2A>, que devuelve `Nothing` si la clave no existe.</span><span class="sxs-lookup"><span data-stu-id="5b09e-119">To prevent this from occurring, use a method, such as <xref:Microsoft.Win32.RegistryKey.GetValue%2A>, that returns `Nothing` if the key does not already exist.</span></span>  
  
## <a name="reading-a-value-from-the-registry"></a><span data-ttu-id="5b09e-120">Leer un valor del Registro</span><span class="sxs-lookup"><span data-stu-id="5b09e-120">Reading a Value from the Registry</span></span>  
 <span data-ttu-id="5b09e-121">En el código siguiente se muestra cómo leer una cadena de HKEY_CURRENT_USER.</span><span class="sxs-lookup"><span data-stu-id="5b09e-121">The following code shows how to read a string from HKEY_CURRENT_USER.</span></span>  
  
 <span data-ttu-id="5b09e-122">[!code-vb[VbResourceTasks#20](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/reading-from-and-writing-to-the-registry-using-the-microsoft-win32-namespace_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="5b09e-122">[!code-vb[VbResourceTasks#20](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/reading-from-and-writing-to-the-registry-using-the-microsoft-win32-namespace_1.vb)]</span></span>  
  
 <span data-ttu-id="5b09e-123">En el código siguiente se lee, se incrementa y, después, se escribe una cadena en HKEY_CURRENT_USER.</span><span class="sxs-lookup"><span data-stu-id="5b09e-123">The following code reads, increments, and then writes a string to HKEY_CURRENT_USER.</span></span>  
  
 <span data-ttu-id="5b09e-124">[!code-vb[VbResourceTasks#21](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/reading-from-and-writing-to-the-registry-using-the-microsoft-win32-namespace_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="5b09e-124">[!code-vb[VbResourceTasks#21](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/reading-from-and-writing-to-the-registry-using-the-microsoft-win32-namespace_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b09e-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b09e-125">See Also</span></span>  
 <span data-ttu-id="5b09e-126"><xref:System.SystemException></span><span class="sxs-lookup"><span data-stu-id="5b09e-126"><xref:System.SystemException></span></span>   
 <span data-ttu-id="5b09e-127"><xref:System.ApplicationException></span><span class="sxs-lookup"><span data-stu-id="5b09e-127"><xref:System.ApplicationException></span></span>   
 <span data-ttu-id="5b09e-128"><xref:Microsoft.VisualBasic.MyServices.RegistryProxy></span><span class="sxs-lookup"><span data-stu-id="5b09e-128"><xref:Microsoft.VisualBasic.MyServices.RegistryProxy></span></span>   
 <span data-ttu-id="5b09e-129">[Try...Catch...Finally (instrucción)](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) </span><span class="sxs-lookup"><span data-stu-id="5b09e-129">[Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) </span></span>  
 <span data-ttu-id="5b09e-130">[Leer y escribir en el Registro](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md) </span><span class="sxs-lookup"><span data-stu-id="5b09e-130">[Reading from and Writing to the Registry](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md) </span></span>  
 [<span data-ttu-id="5b09e-131">Seguridad y Registro</span><span class="sxs-lookup"><span data-stu-id="5b09e-131">Security and the Registry</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md)

