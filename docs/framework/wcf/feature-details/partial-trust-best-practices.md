---
title: "Procedimientos recomendados de confianza parcial | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0d052bc0-5b98-4c50-8bb5-270cc8a8b145
caps.latest.revision: 17
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 17
---
# Procedimientos recomendados de confianza parcial
En este tema se describen procedimientos recomendados al ejecutar [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] en un entorno de confianza parcial.  
  
## Serialización  
 Aplique los siguientes procedimientos al utilizar <xref:System.Runtime.Serialization.DataContractSerializer> en una aplicación de confianza parcial.  
  
-   Se ha de marcar a todos los tipos serializables mediante el atributo `[DataContract]`.Las siguientes técnicas no se admiten en un entorno de confianza parcial:  
  
-   Marcado de clases que se van a serializar con el <xref:System.SerializableAttribute>.  
  
-   Implementación de la interfaz <xref:System.Runtime.Serialization.ISerializable> para permitir que una clase controle su proceso de serialización.  
  
### Uso de DataContractSerializer  
  
-   Todos los tipos marcados con el atributo `[DataContract]` deben ser públicos.Los tipos no públicos no se pueden serializar en un entorno de confianza parcial.  
  
-   Todos los miembros de `[DataContract]` de un tipo de `[DataContract]` serializable deben ser públicos.Un tipo con un `[DataMember]` no público no se puede serializar en un entorno de confianza parcial.  
  
-   Los métodos que administran eventos de serialización \(como `OnSerializing`, `OnSerialized`, `OnDeserializing`y `OnDeserialized`\) se deben declarar como públicos.Sin embargo, se admiten las implementaciones explícitas e implícitas de <xref:System.Runtime.Serialization.IDeserializationCallback.OnDeserialization%28System.Object%29>.  
  
-   Los tipos `[DataContract]` implementados en ensamblados marcados con el <xref:System.Security.AllowPartiallyTrustedCallersAttribute> no deben realizar acciones relacionadas con la seguridad en el constructor de tipos, puesto que el <xref:System.Runtime.Serialization.DataContractSerializer> no llama durante la deserialización al constructor del objeto del que se ha creado recientemente una instancia.Particularmente, se han de evitar las siguientes técnicas de seguridad comunes en los tipos de `[DataContract]`:  
  
-   Intentar restringir el acceso de confianza parcial haciendo interno o privado el constructor del tipo.  
  
-   Restringir el acceso al tipo agregando una `[LinkDemand]` al constructor del tipo.  
  
-   Suponer que, como se ha creado una instancia del objeto correctamente, todas las comprobaciones de validación requeridas por el constructor se han superado con éxito.  
  
### Utilizar IXmlSerializable  
 Los siguientes procedimientos recomendados se aplican a tipos que implementan <xref:System.Xml.Serialization.IXmlSerializable> y se serializan mediante <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
-   Las implementaciones del método estático <xref:System.Xml.Serialization.IXmlSerializable.GetSchema%2A> deben ser `public`.  
  
-   Los métodos de instancia que implementan la interfaz <xref:System.Xml.Serialization.IXmlSerializable> deben ser `public`.  
  
## Utilizar WCF a partir de código de la plataforma de plena confianza que permite llamadas desde llamadores de confianza parcial  
 El modelo de seguridad de confianza parcial de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] supone que cualquier autor de llama de un método o una propiedad pública de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] se ejecuta en el contexto de seguridad de acceso del código \(CAS\) de la aplicación de hospedaje.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] también supone que solo existe un contexto de seguridad de la aplicación para cada <xref:System.AppDomain> y que este contexto lo establece en la hora de creación de <xref:System.AppDomain> un host de confianza \(por ejemplo, mediante una llamada a <xref:System.AppDomain.CreateDomain%2A> o por parte del Administrador de aplicaciones de ASP.NET\).  
  
 Este modelo de seguridad se aplica a las aplicaciones escritas por usuarios que no pueden validar permisos CAS adicionales, como, por ejemplo, el código de usuario que se ejecuta en una aplicación ASP.NET de nivel de confianza medio.Sin embargo, el código de plataforma de plena confianza \(por ejemplo, un ensamblado de otro fabricante que se instala en la caché global de ensamblados y acepta llamadas de código de confianza parcial\) debe tener un cuidado explícito al realizar llamadas en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] en nombre de una aplicación de confianza parcial, para evitar introducir vulnerabilidades de seguridad en el nivel de aplicación.  
  
 El código de plena confianza debería evitar modificar el conjunto de permisos CAS del subproceso actual \(llamando al método <xref:System.Security.PermissionSet.Assert%2A>, <xref:System.Security.PermissionSet.PermitOnly%2A>o <xref:System.Security.PermissionSet.Deny%2A>\) antes de llamar a la API de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] en nombre de código de confianza parcial.Validar, denegar o crear un contexto de permiso para subprocesos que sea independiente del contexto de seguridad de aplicaciones puede provocar un comportamiento inesperado.En función de la aplicación, este comportamiento puede producir vulnerabilidades de seguridad en aplicaciones.  
  
 El código que llama en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utilizando un contexto de permiso para subprocesos debe estar preparado para afrontar las siguientes situaciones que se podrían presentar:  
  
-   El contexto de seguridad específico para subprocesos no se puede mantener durante toda la operación, lo que produce excepciones de seguridad potenciales.  
  
-   El código de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] interno, así como cualquier devolución de llamada proporcionada por el usuario puede ejecutarse en un contexto de seguridad diferente que aquel bajo el que se inició la llamada originariamente.Entre estos contextos se incluyen:  
  
    -   El contexto del permiso de aplicación.  
  
    -   Cualquier contexto de permiso para subprocesos creado previamente por otros subprocesos de usuarios utilizados para llamar en [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] durante la duración del <xref:System.AppDomain> que se está ejecutando actualmente.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] garantiza que el código de confianza parcial no puede obtener permisos de plena confianza a menos que un componente de plena confianza valide tales permisos antes de llamar en las API públicas de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].Sin embargo, no garantiza que los efectos de validar la plena confianza se aíslen a un determinado subproceso, operación o acción del usuario.  
  
 A modo de procedimiento recomendado, evite crear un contexto de permiso para subprocesos llamando al método <xref:System.Security.PermissionSet.Assert%2A>, <xref:System.Security.PermissionSet.PermitOnly%2A> o <xref:System.Security.PermissionSet.Deny%2A>.En su lugar, conceda o deniegue el privilegio a la propia aplicación, para que no se requiera <xref:System.Security.PermissionSet.Assert%2A>, <xref:System.Security.PermissionSet.Deny%2A> o <xref:System.Security.PermissionSet.PermitOnly%2A>.  
  
## Vea también  
 <xref:System.Runtime.Serialization.DataContractSerializer>   
 <xref:System.Xml.Serialization.IXmlSerializable>