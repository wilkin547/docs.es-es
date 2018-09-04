---
title: Colecciones de esquemas de OLE DB
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 1ab6426875b73b400a59b7e4cf155615d7472d05
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43514494"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="8aa1a-102">Colecciones de esquemas de OLE DB</span><span class="sxs-lookup"><span data-stu-id="8aa1a-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="8aa1a-103">En esta sección se describe la compatibilidad de las colecciones de esquemas con los proveedores OLE DB de Microsoft SQL Server, Oracle y Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="8aa1a-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="8aa1a-104">Proveedor OLE DB para Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="8aa1a-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="8aa1a-105">El controlador OLE DB de Microsoft SQL Server admite las siguientes colecciones de esquemas específicas además de las colecciones de esquemas comunes:</span><span class="sxs-lookup"><span data-stu-id="8aa1a-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="8aa1a-106">Tablas</span><span class="sxs-lookup"><span data-stu-id="8aa1a-106">Tables</span></span>  
  
-   <span data-ttu-id="8aa1a-107">Columnas</span><span class="sxs-lookup"><span data-stu-id="8aa1a-107">Columns</span></span>  
  
-   <span data-ttu-id="8aa1a-108">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="8aa1a-108">Procedures</span></span>  
  
-   <span data-ttu-id="8aa1a-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="8aa1a-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="8aa1a-110">Catálogo</span><span class="sxs-lookup"><span data-stu-id="8aa1a-110">Catalog</span></span>  
  
-   <span data-ttu-id="8aa1a-111">Índices</span><span class="sxs-lookup"><span data-stu-id="8aa1a-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="8aa1a-112">Tablas</span><span class="sxs-lookup"><span data-stu-id="8aa1a-112">Tables</span></span>  
  
|<span data-ttu-id="8aa1a-113">ColumName</span><span class="sxs-lookup"><span data-stu-id="8aa1a-113">ColumnName</span></span>|<span data-ttu-id="8aa1a-114">DataType</span><span class="sxs-lookup"><span data-stu-id="8aa1a-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8aa1a-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8aa1a-115">TABLE_CATALOG</span></span>|<span data-ttu-id="8aa1a-116">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-116">String</span></span>|  
|<span data-ttu-id="8aa1a-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8aa1a-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="8aa1a-118">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-118">String</span></span>|  
|<span data-ttu-id="8aa1a-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8aa1a-119">TABLE_NAME</span></span>|<span data-ttu-id="8aa1a-120">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-120">String</span></span>|  
|<span data-ttu-id="8aa1a-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="8aa1a-121">TABLE_TYPE</span></span>|<span data-ttu-id="8aa1a-122">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-122">String</span></span>|  
|<span data-ttu-id="8aa1a-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="8aa1a-123">TABLE_GUID</span></span>|<span data-ttu-id="8aa1a-124">Guid</span><span class="sxs-lookup"><span data-stu-id="8aa1a-124">Guid</span></span>|  
|<span data-ttu-id="8aa1a-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-125">DESCRIPTION</span></span>|<span data-ttu-id="8aa1a-126">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-126">String</span></span>|  
|<span data-ttu-id="8aa1a-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="8aa1a-127">TABLE_PROPID</span></span>|<span data-ttu-id="8aa1a-128">Int64</span><span class="sxs-lookup"><span data-stu-id="8aa1a-128">Int64</span></span>|  
|<span data-ttu-id="8aa1a-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="8aa1a-129">DATE_CREATED</span></span>|<span data-ttu-id="8aa1a-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="8aa1a-130">DateTime</span></span>|  
|<span data-ttu-id="8aa1a-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="8aa1a-131">DATE_MODIFIED</span></span>|<span data-ttu-id="8aa1a-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="8aa1a-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="8aa1a-133">Columnas</span><span class="sxs-lookup"><span data-stu-id="8aa1a-133">Columns</span></span>  
  
|<span data-ttu-id="8aa1a-134">ColumName</span><span class="sxs-lookup"><span data-stu-id="8aa1a-134">ColumnName</span></span>|<span data-ttu-id="8aa1a-135">DataType</span><span class="sxs-lookup"><span data-stu-id="8aa1a-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8aa1a-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8aa1a-136">TABLE_CATALOG</span></span>|<span data-ttu-id="8aa1a-137">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-137">String</span></span>|  
|<span data-ttu-id="8aa1a-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8aa1a-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="8aa1a-139">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-139">String</span></span>|  
|<span data-ttu-id="8aa1a-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8aa1a-140">TABLE_NAME</span></span>|<span data-ttu-id="8aa1a-141">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-141">String</span></span>|  
|<span data-ttu-id="8aa1a-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="8aa1a-142">COLUMN_NAME</span></span>|<span data-ttu-id="8aa1a-143">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-143">String</span></span>|  
|<span data-ttu-id="8aa1a-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="8aa1a-144">COLUMN_GUID</span></span>|<span data-ttu-id="8aa1a-145">Guid</span><span class="sxs-lookup"><span data-stu-id="8aa1a-145">Guid</span></span>|  
|<span data-ttu-id="8aa1a-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="8aa1a-146">COLUMN_PROPID</span></span>|<span data-ttu-id="8aa1a-147">Int64</span><span class="sxs-lookup"><span data-stu-id="8aa1a-147">Int64</span></span>|  
|<span data-ttu-id="8aa1a-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="8aa1a-149">Int64</span><span class="sxs-lookup"><span data-stu-id="8aa1a-149">Int64</span></span>|  
|<span data-ttu-id="8aa1a-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="8aa1a-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="8aa1a-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="8aa1a-151">Boolean</span></span>|  
|<span data-ttu-id="8aa1a-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="8aa1a-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="8aa1a-153">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-153">String</span></span>|  
|<span data-ttu-id="8aa1a-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="8aa1a-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="8aa1a-155">Int64</span><span class="sxs-lookup"><span data-stu-id="8aa1a-155">Int64</span></span>|  
|<span data-ttu-id="8aa1a-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="8aa1a-156">IS_NULLABLE</span></span>|<span data-ttu-id="8aa1a-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="8aa1a-157">Boolean</span></span>|  
|<span data-ttu-id="8aa1a-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="8aa1a-158">DATA_TYPE</span></span>|<span data-ttu-id="8aa1a-159">Int32</span><span class="sxs-lookup"><span data-stu-id="8aa1a-159">Int32</span></span>|  
|<span data-ttu-id="8aa1a-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="8aa1a-160">TYPE_GUID</span></span>|<span data-ttu-id="8aa1a-161">Guid</span><span class="sxs-lookup"><span data-stu-id="8aa1a-161">Guid</span></span>|  
|<span data-ttu-id="8aa1a-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="8aa1a-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="8aa1a-163">Int64</span><span class="sxs-lookup"><span data-stu-id="8aa1a-163">Int64</span></span>|  
|<span data-ttu-id="8aa1a-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="8aa1a-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="8aa1a-165">Int64</span><span class="sxs-lookup"><span data-stu-id="8aa1a-165">Int64</span></span>|  
|<span data-ttu-id="8aa1a-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="8aa1a-167">Int32</span><span class="sxs-lookup"><span data-stu-id="8aa1a-167">Int32</span></span>|  
|<span data-ttu-id="8aa1a-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="8aa1a-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="8aa1a-169">Int16</span><span class="sxs-lookup"><span data-stu-id="8aa1a-169">Int16</span></span>|  
|<span data-ttu-id="8aa1a-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="8aa1a-171">Int64</span><span class="sxs-lookup"><span data-stu-id="8aa1a-171">Int64</span></span>|  
|<span data-ttu-id="8aa1a-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8aa1a-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="8aa1a-173">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-173">String</span></span>|  
|<span data-ttu-id="8aa1a-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8aa1a-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="8aa1a-175">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-175">String</span></span>|  
|<span data-ttu-id="8aa1a-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="8aa1a-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="8aa1a-177">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-177">String</span></span>|  
|<span data-ttu-id="8aa1a-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8aa1a-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="8aa1a-179">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-179">String</span></span>|  
|<span data-ttu-id="8aa1a-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8aa1a-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="8aa1a-181">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-181">String</span></span>|  
|<span data-ttu-id="8aa1a-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="8aa1a-182">COLLATION_NAME</span></span>|<span data-ttu-id="8aa1a-183">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-183">String</span></span>|  
|<span data-ttu-id="8aa1a-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8aa1a-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="8aa1a-185">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-185">String</span></span>|  
|<span data-ttu-id="8aa1a-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8aa1a-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="8aa1a-187">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-187">String</span></span>|  
|<span data-ttu-id="8aa1a-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="8aa1a-188">DOMAIN_NAME</span></span>|<span data-ttu-id="8aa1a-189">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-189">String</span></span>|  
|<span data-ttu-id="8aa1a-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-190">DESCRIPTION</span></span>|<span data-ttu-id="8aa1a-191">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-191">String</span></span>|  
|<span data-ttu-id="8aa1a-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="8aa1a-192">COLUMN_LCID</span></span>|<span data-ttu-id="8aa1a-193">Int32</span><span class="sxs-lookup"><span data-stu-id="8aa1a-193">Int32</span></span>|  
|<span data-ttu-id="8aa1a-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="8aa1a-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="8aa1a-195">Int32</span><span class="sxs-lookup"><span data-stu-id="8aa1a-195">Int32</span></span>|  
|<span data-ttu-id="8aa1a-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="8aa1a-196">COLUMN_SORTID</span></span>|<span data-ttu-id="8aa1a-197">Int32</span><span class="sxs-lookup"><span data-stu-id="8aa1a-197">Int32</span></span>|  
|<span data-ttu-id="8aa1a-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="8aa1a-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="8aa1a-199">Byte[]</span></span>|  
|<span data-ttu-id="8aa1a-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="8aa1a-200">IS_COMPUTED</span></span>|<span data-ttu-id="8aa1a-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="8aa1a-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="8aa1a-202">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="8aa1a-202">Procedures</span></span>  
  
|<span data-ttu-id="8aa1a-203">ColumName</span><span class="sxs-lookup"><span data-stu-id="8aa1a-203">ColumnName</span></span>|<span data-ttu-id="8aa1a-204">DataType</span><span class="sxs-lookup"><span data-stu-id="8aa1a-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8aa1a-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8aa1a-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="8aa1a-206">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-206">String</span></span>|  
|<span data-ttu-id="8aa1a-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8aa1a-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="8aa1a-208">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-208">String</span></span>|  
|<span data-ttu-id="8aa1a-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="8aa1a-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="8aa1a-210">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-210">String</span></span>|  
|<span data-ttu-id="8aa1a-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="8aa1a-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="8aa1a-212">Int16</span><span class="sxs-lookup"><span data-stu-id="8aa1a-212">Int16</span></span>|  
|<span data-ttu-id="8aa1a-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="8aa1a-214">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-214">String</span></span>|  
|<span data-ttu-id="8aa1a-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-215">DESCRIPTION</span></span>|<span data-ttu-id="8aa1a-216">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-216">String</span></span>|  
|<span data-ttu-id="8aa1a-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="8aa1a-217">DATE_CREATED</span></span>|<span data-ttu-id="8aa1a-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="8aa1a-218">DateTime</span></span>|  
|<span data-ttu-id="8aa1a-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="8aa1a-219">DATE_MODIFIED</span></span>|<span data-ttu-id="8aa1a-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="8aa1a-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="8aa1a-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="8aa1a-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="8aa1a-222">ColumName</span><span class="sxs-lookup"><span data-stu-id="8aa1a-222">ColumnName</span></span>|<span data-ttu-id="8aa1a-223">DataType</span><span class="sxs-lookup"><span data-stu-id="8aa1a-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8aa1a-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8aa1a-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="8aa1a-225">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-225">String</span></span>|  
|<span data-ttu-id="8aa1a-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8aa1a-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="8aa1a-227">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-227">String</span></span>|  
|<span data-ttu-id="8aa1a-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="8aa1a-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="8aa1a-229">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-229">String</span></span>|  
|<span data-ttu-id="8aa1a-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="8aa1a-230">PARAMETER_NAME</span></span>|<span data-ttu-id="8aa1a-231">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-231">String</span></span>|  
|<span data-ttu-id="8aa1a-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="8aa1a-233">Int32</span><span class="sxs-lookup"><span data-stu-id="8aa1a-233">Int32</span></span>|  
|<span data-ttu-id="8aa1a-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="8aa1a-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="8aa1a-235">Int32</span><span class="sxs-lookup"><span data-stu-id="8aa1a-235">Int32</span></span>|  
|<span data-ttu-id="8aa1a-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="8aa1a-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="8aa1a-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="8aa1a-237">Boolean</span></span>|  
|<span data-ttu-id="8aa1a-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="8aa1a-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="8aa1a-239">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-239">String</span></span>|  
|<span data-ttu-id="8aa1a-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="8aa1a-240">IS_NULLABLE</span></span>|<span data-ttu-id="8aa1a-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="8aa1a-241">Boolean</span></span>|  
|<span data-ttu-id="8aa1a-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="8aa1a-242">DATA_TYPE</span></span>|<span data-ttu-id="8aa1a-243">Int32</span><span class="sxs-lookup"><span data-stu-id="8aa1a-243">Int32</span></span>|  
|<span data-ttu-id="8aa1a-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="8aa1a-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="8aa1a-245">Int64</span><span class="sxs-lookup"><span data-stu-id="8aa1a-245">Int64</span></span>|  
|<span data-ttu-id="8aa1a-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="8aa1a-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="8aa1a-247">Int64</span><span class="sxs-lookup"><span data-stu-id="8aa1a-247">Int64</span></span>|  
|<span data-ttu-id="8aa1a-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="8aa1a-249">Int32</span><span class="sxs-lookup"><span data-stu-id="8aa1a-249">Int32</span></span>|  
|<span data-ttu-id="8aa1a-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="8aa1a-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="8aa1a-251">Int16</span><span class="sxs-lookup"><span data-stu-id="8aa1a-251">Int16</span></span>|  
|<span data-ttu-id="8aa1a-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-252">DESCRIPTION</span></span>|<span data-ttu-id="8aa1a-253">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-253">String</span></span>|  
|<span data-ttu-id="8aa1a-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="8aa1a-254">TYPE_NAME</span></span>|<span data-ttu-id="8aa1a-255">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-255">String</span></span>|  
|<span data-ttu-id="8aa1a-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="8aa1a-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="8aa1a-257">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="8aa1a-258">Catálogo</span><span class="sxs-lookup"><span data-stu-id="8aa1a-258">Catalog</span></span>  
  
|<span data-ttu-id="8aa1a-259">ColumName</span><span class="sxs-lookup"><span data-stu-id="8aa1a-259">ColumnName</span></span>|<span data-ttu-id="8aa1a-260">DataType</span><span class="sxs-lookup"><span data-stu-id="8aa1a-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8aa1a-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="8aa1a-261">CATALOG_NAME</span></span>|<span data-ttu-id="8aa1a-262">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-262">String</span></span>|  
|<span data-ttu-id="8aa1a-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-263">DESCRIPTION</span></span>|<span data-ttu-id="8aa1a-264">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="8aa1a-265">Índices</span><span class="sxs-lookup"><span data-stu-id="8aa1a-265">Indexes</span></span>  
  
|<span data-ttu-id="8aa1a-266">ColumName</span><span class="sxs-lookup"><span data-stu-id="8aa1a-266">ColumnName</span></span>|<span data-ttu-id="8aa1a-267">DataType</span><span class="sxs-lookup"><span data-stu-id="8aa1a-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8aa1a-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8aa1a-268">TABLE_CATALOG</span></span>|<span data-ttu-id="8aa1a-269">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-269">String</span></span>|  
|<span data-ttu-id="8aa1a-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8aa1a-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="8aa1a-271">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-271">String</span></span>|  
|<span data-ttu-id="8aa1a-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8aa1a-272">TABLE_NAME</span></span>|<span data-ttu-id="8aa1a-273">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-273">String</span></span>|  
|<span data-ttu-id="8aa1a-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8aa1a-274">INDEX_CATALOG</span></span>|<span data-ttu-id="8aa1a-275">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-275">String</span></span>|  
|<span data-ttu-id="8aa1a-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8aa1a-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="8aa1a-277">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-277">String</span></span>|  
|<span data-ttu-id="8aa1a-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="8aa1a-278">INDEX_NAME</span></span>|<span data-ttu-id="8aa1a-279">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-279">String</span></span>|  
|<span data-ttu-id="8aa1a-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="8aa1a-280">PRIMARY_KEY</span></span>|<span data-ttu-id="8aa1a-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="8aa1a-281">Boolean</span></span>|  
|<span data-ttu-id="8aa1a-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="8aa1a-282">UNIQUE</span></span>|<span data-ttu-id="8aa1a-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="8aa1a-283">Boolean</span></span>|  
|<span data-ttu-id="8aa1a-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="8aa1a-284">CLUSTERED</span></span>|<span data-ttu-id="8aa1a-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="8aa1a-285">Boolean</span></span>|  
|<span data-ttu-id="8aa1a-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="8aa1a-286">TYPE</span></span>|<span data-ttu-id="8aa1a-287">Int32</span><span class="sxs-lookup"><span data-stu-id="8aa1a-287">Int32</span></span>|  
|<span data-ttu-id="8aa1a-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="8aa1a-288">FILL_FACTOR</span></span>|<span data-ttu-id="8aa1a-289">Int32</span><span class="sxs-lookup"><span data-stu-id="8aa1a-289">Int32</span></span>|  
|<span data-ttu-id="8aa1a-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="8aa1a-290">INITIAL_SIZE</span></span>|<span data-ttu-id="8aa1a-291">Int32</span><span class="sxs-lookup"><span data-stu-id="8aa1a-291">Int32</span></span>|  
|<span data-ttu-id="8aa1a-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="8aa1a-292">NULLS</span></span>|<span data-ttu-id="8aa1a-293">Int32</span><span class="sxs-lookup"><span data-stu-id="8aa1a-293">Int32</span></span>|  
|<span data-ttu-id="8aa1a-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="8aa1a-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="8aa1a-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="8aa1a-295">Boolean</span></span>|  
|<span data-ttu-id="8aa1a-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="8aa1a-296">AUTO_UPDATE</span></span>|<span data-ttu-id="8aa1a-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="8aa1a-297">Boolean</span></span>|  
|<span data-ttu-id="8aa1a-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-298">NULL_COLLATION</span></span>|<span data-ttu-id="8aa1a-299">Int32</span><span class="sxs-lookup"><span data-stu-id="8aa1a-299">Int32</span></span>|  
|<span data-ttu-id="8aa1a-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="8aa1a-301">Int64</span><span class="sxs-lookup"><span data-stu-id="8aa1a-301">Int64</span></span>|  
|<span data-ttu-id="8aa1a-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="8aa1a-302">COLUMN_NAME</span></span>|<span data-ttu-id="8aa1a-303">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-303">String</span></span>|  
|<span data-ttu-id="8aa1a-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="8aa1a-304">COLUMN_GUID</span></span>|<span data-ttu-id="8aa1a-305">Guid</span><span class="sxs-lookup"><span data-stu-id="8aa1a-305">Guid</span></span>|  
|<span data-ttu-id="8aa1a-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="8aa1a-306">COLUMN_PROPID</span></span>|<span data-ttu-id="8aa1a-307">Int64</span><span class="sxs-lookup"><span data-stu-id="8aa1a-307">Int64</span></span>|  
|<span data-ttu-id="8aa1a-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-308">COLLATION</span></span>|<span data-ttu-id="8aa1a-309">Int16</span><span class="sxs-lookup"><span data-stu-id="8aa1a-309">Int16</span></span>|  
|<span data-ttu-id="8aa1a-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="8aa1a-310">CARDINALITY</span></span>|<span data-ttu-id="8aa1a-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="8aa1a-311">Decimal</span></span>|  
|<span data-ttu-id="8aa1a-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="8aa1a-312">PAGES</span></span>|<span data-ttu-id="8aa1a-313">Int32</span><span class="sxs-lookup"><span data-stu-id="8aa1a-313">Int32</span></span>|  
|<span data-ttu-id="8aa1a-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-314">FILTER_CONDITION</span></span>|<span data-ttu-id="8aa1a-315">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-315">String</span></span>|  
|<span data-ttu-id="8aa1a-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="8aa1a-316">INTEGRATED</span></span>|<span data-ttu-id="8aa1a-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="8aa1a-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="8aa1a-318">Proveedor OLE DB de Microsoft para Oracle</span><span class="sxs-lookup"><span data-stu-id="8aa1a-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="8aa1a-319">El controlador OLE DB de Microsoft para Oracle admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="8aa1a-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="8aa1a-320">Tablas</span><span class="sxs-lookup"><span data-stu-id="8aa1a-320">Tables</span></span>  
  
-   <span data-ttu-id="8aa1a-321">Columnas</span><span class="sxs-lookup"><span data-stu-id="8aa1a-321">Columns</span></span>  
  
-   <span data-ttu-id="8aa1a-322">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="8aa1a-322">Procedures</span></span>  
  
-   <span data-ttu-id="8aa1a-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="8aa1a-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="8aa1a-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="8aa1a-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="8aa1a-325">Vistas</span><span class="sxs-lookup"><span data-stu-id="8aa1a-325">Views</span></span>  
  
-   <span data-ttu-id="8aa1a-326">Índices</span><span class="sxs-lookup"><span data-stu-id="8aa1a-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="8aa1a-327">Tablas</span><span class="sxs-lookup"><span data-stu-id="8aa1a-327">Tables</span></span>  
  
|<span data-ttu-id="8aa1a-328">ColumName</span><span class="sxs-lookup"><span data-stu-id="8aa1a-328">ColumnName</span></span>|<span data-ttu-id="8aa1a-329">DataType</span><span class="sxs-lookup"><span data-stu-id="8aa1a-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8aa1a-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8aa1a-330">TABLE_CATALOG</span></span>|<span data-ttu-id="8aa1a-331">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-331">String</span></span>|  
|<span data-ttu-id="8aa1a-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8aa1a-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="8aa1a-333">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-333">String</span></span>|  
|<span data-ttu-id="8aa1a-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8aa1a-334">TABLE_NAME</span></span>|<span data-ttu-id="8aa1a-335">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-335">String</span></span>|  
|<span data-ttu-id="8aa1a-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="8aa1a-336">TABLE_TYPE</span></span>|<span data-ttu-id="8aa1a-337">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-337">String</span></span>|  
|<span data-ttu-id="8aa1a-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="8aa1a-338">TABLE_GUID</span></span>|<span data-ttu-id="8aa1a-339">Guid</span><span class="sxs-lookup"><span data-stu-id="8aa1a-339">Guid</span></span>|  
|<span data-ttu-id="8aa1a-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-340">DESCRIPTION</span></span>|<span data-ttu-id="8aa1a-341">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-341">String</span></span>|  
|<span data-ttu-id="8aa1a-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="8aa1a-342">TABLE_PROPID</span></span>|<span data-ttu-id="8aa1a-343">Int64</span><span class="sxs-lookup"><span data-stu-id="8aa1a-343">Int64</span></span>|  
|<span data-ttu-id="8aa1a-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="8aa1a-344">DATE_CREATED</span></span>|<span data-ttu-id="8aa1a-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="8aa1a-345">DateTime</span></span>|  
|<span data-ttu-id="8aa1a-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="8aa1a-346">DATE_MODIFIED</span></span>|<span data-ttu-id="8aa1a-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="8aa1a-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="8aa1a-348">Columnas</span><span class="sxs-lookup"><span data-stu-id="8aa1a-348">Columns</span></span>  
  
|<span data-ttu-id="8aa1a-349">ColumName</span><span class="sxs-lookup"><span data-stu-id="8aa1a-349">ColumnName</span></span>|<span data-ttu-id="8aa1a-350">DataType</span><span class="sxs-lookup"><span data-stu-id="8aa1a-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8aa1a-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8aa1a-351">TABLE_CATALOG</span></span>|<span data-ttu-id="8aa1a-352">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-352">String</span></span>|  
|<span data-ttu-id="8aa1a-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8aa1a-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="8aa1a-354">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-354">String</span></span>|  
|<span data-ttu-id="8aa1a-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8aa1a-355">TABLE_NAME</span></span>|<span data-ttu-id="8aa1a-356">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-356">String</span></span>|  
|<span data-ttu-id="8aa1a-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="8aa1a-357">COLUMN_NAME</span></span>|<span data-ttu-id="8aa1a-358">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-358">String</span></span>|  
|<span data-ttu-id="8aa1a-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="8aa1a-359">COLUMN_GUID</span></span>|<span data-ttu-id="8aa1a-360">Guid</span><span class="sxs-lookup"><span data-stu-id="8aa1a-360">Guid</span></span>|  
|<span data-ttu-id="8aa1a-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="8aa1a-361">COLUMN_PROPID</span></span>|<span data-ttu-id="8aa1a-362">Int64</span><span class="sxs-lookup"><span data-stu-id="8aa1a-362">Int64</span></span>|  
|<span data-ttu-id="8aa1a-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="8aa1a-364">Int64</span><span class="sxs-lookup"><span data-stu-id="8aa1a-364">Int64</span></span>|  
|<span data-ttu-id="8aa1a-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="8aa1a-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="8aa1a-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="8aa1a-366">Boolean</span></span>|  
|<span data-ttu-id="8aa1a-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="8aa1a-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="8aa1a-368">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-368">String</span></span>|  
|<span data-ttu-id="8aa1a-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="8aa1a-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="8aa1a-370">Int64</span><span class="sxs-lookup"><span data-stu-id="8aa1a-370">Int64</span></span>|  
|<span data-ttu-id="8aa1a-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="8aa1a-371">IS_NULLABLE</span></span>|<span data-ttu-id="8aa1a-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="8aa1a-372">Boolean</span></span>|  
|<span data-ttu-id="8aa1a-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="8aa1a-373">DATA_TYPE</span></span>|<span data-ttu-id="8aa1a-374">Int32</span><span class="sxs-lookup"><span data-stu-id="8aa1a-374">Int32</span></span>|  
|<span data-ttu-id="8aa1a-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="8aa1a-375">TYPE_GUID</span></span>|<span data-ttu-id="8aa1a-376">Guid</span><span class="sxs-lookup"><span data-stu-id="8aa1a-376">Guid</span></span>|  
|<span data-ttu-id="8aa1a-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="8aa1a-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="8aa1a-378">Int64</span><span class="sxs-lookup"><span data-stu-id="8aa1a-378">Int64</span></span>|  
|<span data-ttu-id="8aa1a-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="8aa1a-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="8aa1a-380">Int64</span><span class="sxs-lookup"><span data-stu-id="8aa1a-380">Int64</span></span>|  
|<span data-ttu-id="8aa1a-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="8aa1a-382">Int32</span><span class="sxs-lookup"><span data-stu-id="8aa1a-382">Int32</span></span>|  
|<span data-ttu-id="8aa1a-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="8aa1a-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="8aa1a-384">Int16</span><span class="sxs-lookup"><span data-stu-id="8aa1a-384">Int16</span></span>|  
|<span data-ttu-id="8aa1a-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="8aa1a-386">Int64</span><span class="sxs-lookup"><span data-stu-id="8aa1a-386">Int64</span></span>|  
|<span data-ttu-id="8aa1a-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8aa1a-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="8aa1a-388">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-388">String</span></span>|  
|<span data-ttu-id="8aa1a-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8aa1a-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="8aa1a-390">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-390">String</span></span>|  
|<span data-ttu-id="8aa1a-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="8aa1a-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="8aa1a-392">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-392">String</span></span>|  
|<span data-ttu-id="8aa1a-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8aa1a-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="8aa1a-394">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-394">String</span></span>|  
|<span data-ttu-id="8aa1a-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8aa1a-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="8aa1a-396">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-396">String</span></span>|  
|<span data-ttu-id="8aa1a-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="8aa1a-397">COLLATION_NAME</span></span>|<span data-ttu-id="8aa1a-398">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-398">String</span></span>|  
|<span data-ttu-id="8aa1a-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8aa1a-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="8aa1a-400">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-400">String</span></span>|  
|<span data-ttu-id="8aa1a-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8aa1a-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="8aa1a-402">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-402">String</span></span>|  
|<span data-ttu-id="8aa1a-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="8aa1a-403">DOMAIN_NAME</span></span>|<span data-ttu-id="8aa1a-404">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-404">String</span></span>|  
|<span data-ttu-id="8aa1a-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-405">DESCRIPTION</span></span>|<span data-ttu-id="8aa1a-406">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="8aa1a-407">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="8aa1a-407">Procedures</span></span>  
  
|<span data-ttu-id="8aa1a-408">ColumName</span><span class="sxs-lookup"><span data-stu-id="8aa1a-408">ColumnName</span></span>|<span data-ttu-id="8aa1a-409">DataType</span><span class="sxs-lookup"><span data-stu-id="8aa1a-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8aa1a-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8aa1a-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="8aa1a-411">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-411">String</span></span>|  
|<span data-ttu-id="8aa1a-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8aa1a-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="8aa1a-413">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-413">String</span></span>|  
|<span data-ttu-id="8aa1a-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="8aa1a-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="8aa1a-415">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-415">String</span></span>|  
|<span data-ttu-id="8aa1a-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="8aa1a-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="8aa1a-417">Int16</span><span class="sxs-lookup"><span data-stu-id="8aa1a-417">Int16</span></span>|  
|<span data-ttu-id="8aa1a-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="8aa1a-419">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-419">String</span></span>|  
|<span data-ttu-id="8aa1a-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-420">DESCRIPTION</span></span>|<span data-ttu-id="8aa1a-421">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-421">String</span></span>|  
|<span data-ttu-id="8aa1a-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="8aa1a-422">DATE_CREATED</span></span>|<span data-ttu-id="8aa1a-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="8aa1a-423">DateTime</span></span>|  
|<span data-ttu-id="8aa1a-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="8aa1a-424">DATE_MODIFIED</span></span>|<span data-ttu-id="8aa1a-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="8aa1a-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="8aa1a-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="8aa1a-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="8aa1a-427">ColumName</span><span class="sxs-lookup"><span data-stu-id="8aa1a-427">ColumnName</span></span>|<span data-ttu-id="8aa1a-428">DataType</span><span class="sxs-lookup"><span data-stu-id="8aa1a-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8aa1a-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8aa1a-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="8aa1a-430">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-430">String</span></span>|  
|<span data-ttu-id="8aa1a-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8aa1a-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="8aa1a-432">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-432">String</span></span>|  
|<span data-ttu-id="8aa1a-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="8aa1a-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="8aa1a-434">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-434">String</span></span>|  
|<span data-ttu-id="8aa1a-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="8aa1a-435">COLUMN_NAME</span></span>|<span data-ttu-id="8aa1a-436">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-436">String</span></span>|  
|<span data-ttu-id="8aa1a-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="8aa1a-437">COLUMN_GUID</span></span>|<span data-ttu-id="8aa1a-438">Guid</span><span class="sxs-lookup"><span data-stu-id="8aa1a-438">Guid</span></span>|  
|<span data-ttu-id="8aa1a-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="8aa1a-439">COLUMN_PROPID</span></span>|<span data-ttu-id="8aa1a-440">Int64</span><span class="sxs-lookup"><span data-stu-id="8aa1a-440">Int64</span></span>|  
|<span data-ttu-id="8aa1a-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="8aa1a-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="8aa1a-442">Int64</span><span class="sxs-lookup"><span data-stu-id="8aa1a-442">Int64</span></span>|  
|<span data-ttu-id="8aa1a-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="8aa1a-444">Int64</span><span class="sxs-lookup"><span data-stu-id="8aa1a-444">Int64</span></span>|  
|<span data-ttu-id="8aa1a-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="8aa1a-445">IS_NULLABLE</span></span>|<span data-ttu-id="8aa1a-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="8aa1a-446">Boolean</span></span>|  
|<span data-ttu-id="8aa1a-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="8aa1a-447">DATA_TYPE</span></span>|<span data-ttu-id="8aa1a-448">Int32</span><span class="sxs-lookup"><span data-stu-id="8aa1a-448">Int32</span></span>|  
|<span data-ttu-id="8aa1a-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="8aa1a-449">TYPE_GUID</span></span>|<span data-ttu-id="8aa1a-450">Guid</span><span class="sxs-lookup"><span data-stu-id="8aa1a-450">Guid</span></span>|  
|<span data-ttu-id="8aa1a-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="8aa1a-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="8aa1a-452">Int64</span><span class="sxs-lookup"><span data-stu-id="8aa1a-452">Int64</span></span>|  
|<span data-ttu-id="8aa1a-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="8aa1a-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="8aa1a-454">Int64</span><span class="sxs-lookup"><span data-stu-id="8aa1a-454">Int64</span></span>|  
|<span data-ttu-id="8aa1a-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="8aa1a-456">Int32</span><span class="sxs-lookup"><span data-stu-id="8aa1a-456">Int32</span></span>|  
|<span data-ttu-id="8aa1a-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="8aa1a-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="8aa1a-458">Int16</span><span class="sxs-lookup"><span data-stu-id="8aa1a-458">Int16</span></span>|  
|<span data-ttu-id="8aa1a-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-459">DESCRIPTION</span></span>|<span data-ttu-id="8aa1a-460">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-460">String</span></span>|  
|<span data-ttu-id="8aa1a-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="8aa1a-461">OVERLOAD</span></span>|<span data-ttu-id="8aa1a-462">Int16</span><span class="sxs-lookup"><span data-stu-id="8aa1a-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="8aa1a-463">Vistas</span><span class="sxs-lookup"><span data-stu-id="8aa1a-463">Views</span></span>  
  
|<span data-ttu-id="8aa1a-464">ColumName</span><span class="sxs-lookup"><span data-stu-id="8aa1a-464">ColumnName</span></span>|<span data-ttu-id="8aa1a-465">DataType</span><span class="sxs-lookup"><span data-stu-id="8aa1a-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8aa1a-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8aa1a-466">TABLE_CATALOG</span></span>|<span data-ttu-id="8aa1a-467">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-467">String</span></span>|  
|<span data-ttu-id="8aa1a-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8aa1a-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="8aa1a-469">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-469">String</span></span>|  
|<span data-ttu-id="8aa1a-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8aa1a-470">TABLE_NAME</span></span>|<span data-ttu-id="8aa1a-471">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-471">String</span></span>|  
|<span data-ttu-id="8aa1a-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="8aa1a-473">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-473">String</span></span>|  
|<span data-ttu-id="8aa1a-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-474">CHECK_OPTION</span></span>|<span data-ttu-id="8aa1a-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="8aa1a-475">Boolean</span></span>|  
|<span data-ttu-id="8aa1a-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="8aa1a-476">IS_UPDATABLE</span></span>|<span data-ttu-id="8aa1a-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="8aa1a-477">Boolean</span></span>|  
|<span data-ttu-id="8aa1a-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-478">DESCRIPTION</span></span>|<span data-ttu-id="8aa1a-479">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-479">String</span></span>|  
|<span data-ttu-id="8aa1a-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="8aa1a-480">DATE_CREATED</span></span>|<span data-ttu-id="8aa1a-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="8aa1a-481">DateTime</span></span>|  
|<span data-ttu-id="8aa1a-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="8aa1a-482">DATE_MODIFIED</span></span>|<span data-ttu-id="8aa1a-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="8aa1a-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="8aa1a-484">Índices</span><span class="sxs-lookup"><span data-stu-id="8aa1a-484">Indexes</span></span>  
  
|<span data-ttu-id="8aa1a-485">ColumName</span><span class="sxs-lookup"><span data-stu-id="8aa1a-485">ColumnName</span></span>|<span data-ttu-id="8aa1a-486">DataType</span><span class="sxs-lookup"><span data-stu-id="8aa1a-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8aa1a-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8aa1a-487">TABLE_CATALOG</span></span>|<span data-ttu-id="8aa1a-488">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-488">String</span></span>|  
|<span data-ttu-id="8aa1a-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8aa1a-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="8aa1a-490">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-490">String</span></span>|  
|<span data-ttu-id="8aa1a-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8aa1a-491">TABLE_NAME</span></span>|<span data-ttu-id="8aa1a-492">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-492">String</span></span>|  
|<span data-ttu-id="8aa1a-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8aa1a-493">INDEX_CATALOG</span></span>|<span data-ttu-id="8aa1a-494">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-494">String</span></span>|  
|<span data-ttu-id="8aa1a-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8aa1a-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="8aa1a-496">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-496">String</span></span>|  
|<span data-ttu-id="8aa1a-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="8aa1a-497">INDEX_NAME</span></span>|<span data-ttu-id="8aa1a-498">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-498">String</span></span>|  
|<span data-ttu-id="8aa1a-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="8aa1a-499">PRIMARY_KEY</span></span>|<span data-ttu-id="8aa1a-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="8aa1a-500">Boolean</span></span>|  
|<span data-ttu-id="8aa1a-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="8aa1a-501">UNIQUE</span></span>|<span data-ttu-id="8aa1a-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="8aa1a-502">Boolean</span></span>|  
|<span data-ttu-id="8aa1a-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="8aa1a-503">CLUSTERED</span></span>|<span data-ttu-id="8aa1a-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="8aa1a-504">Boolean</span></span>|  
|<span data-ttu-id="8aa1a-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="8aa1a-505">TYPE</span></span>|<span data-ttu-id="8aa1a-506">Int32</span><span class="sxs-lookup"><span data-stu-id="8aa1a-506">Int32</span></span>|  
|<span data-ttu-id="8aa1a-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="8aa1a-507">FILL_FACTOR</span></span>|<span data-ttu-id="8aa1a-508">Int32</span><span class="sxs-lookup"><span data-stu-id="8aa1a-508">Int32</span></span>|  
|<span data-ttu-id="8aa1a-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="8aa1a-509">INITIAL_SIZE</span></span>|<span data-ttu-id="8aa1a-510">Int32</span><span class="sxs-lookup"><span data-stu-id="8aa1a-510">Int32</span></span>|  
|<span data-ttu-id="8aa1a-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="8aa1a-511">NULLS</span></span>|<span data-ttu-id="8aa1a-512">Int32</span><span class="sxs-lookup"><span data-stu-id="8aa1a-512">Int32</span></span>|  
|<span data-ttu-id="8aa1a-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="8aa1a-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="8aa1a-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="8aa1a-514">Boolean</span></span>|  
|<span data-ttu-id="8aa1a-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="8aa1a-515">AUTO_UPDATE</span></span>|<span data-ttu-id="8aa1a-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="8aa1a-516">Boolean</span></span>|  
|<span data-ttu-id="8aa1a-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-517">NULL_COLLATION</span></span>|<span data-ttu-id="8aa1a-518">Int32</span><span class="sxs-lookup"><span data-stu-id="8aa1a-518">Int32</span></span>|  
|<span data-ttu-id="8aa1a-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="8aa1a-520">Int64</span><span class="sxs-lookup"><span data-stu-id="8aa1a-520">Int64</span></span>|  
|<span data-ttu-id="8aa1a-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="8aa1a-521">COLUMN_NAME</span></span>|<span data-ttu-id="8aa1a-522">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-522">String</span></span>|  
|<span data-ttu-id="8aa1a-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="8aa1a-523">COLUMN_GUID</span></span>|<span data-ttu-id="8aa1a-524">Guid</span><span class="sxs-lookup"><span data-stu-id="8aa1a-524">Guid</span></span>|  
|<span data-ttu-id="8aa1a-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="8aa1a-525">COLUMN_PROPID</span></span>|<span data-ttu-id="8aa1a-526">Int64</span><span class="sxs-lookup"><span data-stu-id="8aa1a-526">Int64</span></span>|  
|<span data-ttu-id="8aa1a-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-527">COLLATION</span></span>|<span data-ttu-id="8aa1a-528">Int16</span><span class="sxs-lookup"><span data-stu-id="8aa1a-528">Int16</span></span>|  
|<span data-ttu-id="8aa1a-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="8aa1a-529">CARDINALITY</span></span>|<span data-ttu-id="8aa1a-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="8aa1a-530">Decimal</span></span>|  
|<span data-ttu-id="8aa1a-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="8aa1a-531">PAGES</span></span>|<span data-ttu-id="8aa1a-532">Int32</span><span class="sxs-lookup"><span data-stu-id="8aa1a-532">Int32</span></span>|  
|<span data-ttu-id="8aa1a-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-533">FILTER_CONDITION</span></span>|<span data-ttu-id="8aa1a-534">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-534">String</span></span>|  
|<span data-ttu-id="8aa1a-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="8aa1a-535">INTEGRATED</span></span>|<span data-ttu-id="8aa1a-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="8aa1a-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="8aa1a-537">Proveedor OLE DB de Microsoft para Jet</span><span class="sxs-lookup"><span data-stu-id="8aa1a-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="8aa1a-538">El controlador OLE DB de Microsoft para Jet admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="8aa1a-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="8aa1a-539">Tablas</span><span class="sxs-lookup"><span data-stu-id="8aa1a-539">Tables</span></span>  
  
-   <span data-ttu-id="8aa1a-540">Columnas</span><span class="sxs-lookup"><span data-stu-id="8aa1a-540">Columns</span></span>  
  
-   <span data-ttu-id="8aa1a-541">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="8aa1a-541">Procedures</span></span>  
  
-   <span data-ttu-id="8aa1a-542">Vistas</span><span class="sxs-lookup"><span data-stu-id="8aa1a-542">Views</span></span>  
  
-   <span data-ttu-id="8aa1a-543">Índices</span><span class="sxs-lookup"><span data-stu-id="8aa1a-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="8aa1a-544">Tablas</span><span class="sxs-lookup"><span data-stu-id="8aa1a-544">Tables</span></span>  
  
|<span data-ttu-id="8aa1a-545">ColumName</span><span class="sxs-lookup"><span data-stu-id="8aa1a-545">ColumnName</span></span>|<span data-ttu-id="8aa1a-546">DataType</span><span class="sxs-lookup"><span data-stu-id="8aa1a-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8aa1a-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8aa1a-547">TABLE_CATALOG</span></span>|<span data-ttu-id="8aa1a-548">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-548">String</span></span>|  
|<span data-ttu-id="8aa1a-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8aa1a-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="8aa1a-550">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-550">String</span></span>|  
|<span data-ttu-id="8aa1a-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8aa1a-551">TABLE_NAME</span></span>|<span data-ttu-id="8aa1a-552">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-552">String</span></span>|  
|<span data-ttu-id="8aa1a-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="8aa1a-553">TABLE_TYPE</span></span>|<span data-ttu-id="8aa1a-554">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-554">String</span></span>|  
|<span data-ttu-id="8aa1a-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="8aa1a-555">TABLE_GUID</span></span>|<span data-ttu-id="8aa1a-556">Guid</span><span class="sxs-lookup"><span data-stu-id="8aa1a-556">Guid</span></span>|  
|<span data-ttu-id="8aa1a-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-557">DESCRIPTION</span></span>|<span data-ttu-id="8aa1a-558">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-558">String</span></span>|  
|<span data-ttu-id="8aa1a-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="8aa1a-559">TABLE_PROPID</span></span>|<span data-ttu-id="8aa1a-560">Int64</span><span class="sxs-lookup"><span data-stu-id="8aa1a-560">Int64</span></span>|  
|<span data-ttu-id="8aa1a-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="8aa1a-561">DATE_CREATED</span></span>|<span data-ttu-id="8aa1a-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="8aa1a-562">DateTime</span></span>|  
|<span data-ttu-id="8aa1a-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="8aa1a-563">DATE_MODIFIED</span></span>|<span data-ttu-id="8aa1a-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="8aa1a-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="8aa1a-565">Columnas</span><span class="sxs-lookup"><span data-stu-id="8aa1a-565">Columns</span></span>  
  
|<span data-ttu-id="8aa1a-566">ColumName</span><span class="sxs-lookup"><span data-stu-id="8aa1a-566">ColumnName</span></span>|<span data-ttu-id="8aa1a-567">DataType</span><span class="sxs-lookup"><span data-stu-id="8aa1a-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8aa1a-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8aa1a-568">TABLE_CATALOG</span></span>|<span data-ttu-id="8aa1a-569">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-569">String</span></span>|  
|<span data-ttu-id="8aa1a-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8aa1a-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="8aa1a-571">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-571">String</span></span>|  
|<span data-ttu-id="8aa1a-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8aa1a-572">TABLE_NAME</span></span>|<span data-ttu-id="8aa1a-573">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-573">String</span></span>|  
|<span data-ttu-id="8aa1a-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="8aa1a-574">COLUMN_NAME</span></span>|<span data-ttu-id="8aa1a-575">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-575">String</span></span>|  
|<span data-ttu-id="8aa1a-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="8aa1a-576">COLUMN_GUID</span></span>|<span data-ttu-id="8aa1a-577">Guid</span><span class="sxs-lookup"><span data-stu-id="8aa1a-577">Guid</span></span>|  
|<span data-ttu-id="8aa1a-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="8aa1a-578">COLUMN_PROPID</span></span>|<span data-ttu-id="8aa1a-579">Int64</span><span class="sxs-lookup"><span data-stu-id="8aa1a-579">Int64</span></span>|  
|<span data-ttu-id="8aa1a-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="8aa1a-581">Int64</span><span class="sxs-lookup"><span data-stu-id="8aa1a-581">Int64</span></span>|  
|<span data-ttu-id="8aa1a-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="8aa1a-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="8aa1a-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="8aa1a-583">Boolean</span></span>|  
|<span data-ttu-id="8aa1a-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="8aa1a-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="8aa1a-585">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-585">String</span></span>|  
|<span data-ttu-id="8aa1a-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="8aa1a-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="8aa1a-587">Int64</span><span class="sxs-lookup"><span data-stu-id="8aa1a-587">Int64</span></span>|  
|<span data-ttu-id="8aa1a-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="8aa1a-588">IS_NULLABLE</span></span>|<span data-ttu-id="8aa1a-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="8aa1a-589">Boolean</span></span>|  
|<span data-ttu-id="8aa1a-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="8aa1a-590">DATA_TYPE</span></span>|<span data-ttu-id="8aa1a-591">Int32</span><span class="sxs-lookup"><span data-stu-id="8aa1a-591">Int32</span></span>|  
|<span data-ttu-id="8aa1a-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="8aa1a-592">TYPE_GUID</span></span>|<span data-ttu-id="8aa1a-593">Guid</span><span class="sxs-lookup"><span data-stu-id="8aa1a-593">Guid</span></span>|  
|<span data-ttu-id="8aa1a-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="8aa1a-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="8aa1a-595">Int64</span><span class="sxs-lookup"><span data-stu-id="8aa1a-595">Int64</span></span>|  
|<span data-ttu-id="8aa1a-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="8aa1a-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="8aa1a-597">Int64</span><span class="sxs-lookup"><span data-stu-id="8aa1a-597">Int64</span></span>|  
|<span data-ttu-id="8aa1a-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="8aa1a-599">Int32</span><span class="sxs-lookup"><span data-stu-id="8aa1a-599">Int32</span></span>|  
|<span data-ttu-id="8aa1a-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="8aa1a-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="8aa1a-601">Int16</span><span class="sxs-lookup"><span data-stu-id="8aa1a-601">Int16</span></span>|  
|<span data-ttu-id="8aa1a-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="8aa1a-603">Int64</span><span class="sxs-lookup"><span data-stu-id="8aa1a-603">Int64</span></span>|  
|<span data-ttu-id="8aa1a-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8aa1a-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="8aa1a-605">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-605">String</span></span>|  
|<span data-ttu-id="8aa1a-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8aa1a-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="8aa1a-607">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-607">String</span></span>|  
|<span data-ttu-id="8aa1a-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="8aa1a-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="8aa1a-609">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-609">String</span></span>|  
|<span data-ttu-id="8aa1a-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8aa1a-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="8aa1a-611">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-611">String</span></span>|  
|<span data-ttu-id="8aa1a-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8aa1a-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="8aa1a-613">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-613">String</span></span>|  
|<span data-ttu-id="8aa1a-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="8aa1a-614">COLLATION_NAME</span></span>|<span data-ttu-id="8aa1a-615">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-615">String</span></span>|  
|<span data-ttu-id="8aa1a-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8aa1a-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="8aa1a-617">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-617">String</span></span>|  
|<span data-ttu-id="8aa1a-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8aa1a-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="8aa1a-619">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-619">String</span></span>|  
|<span data-ttu-id="8aa1a-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="8aa1a-620">DOMAIN_NAME</span></span>|<span data-ttu-id="8aa1a-621">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-621">String</span></span>|  
|<span data-ttu-id="8aa1a-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-622">DESCRIPTION</span></span>|<span data-ttu-id="8aa1a-623">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="8aa1a-624">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="8aa1a-624">Procedures</span></span>  
  
|<span data-ttu-id="8aa1a-625">ColumName</span><span class="sxs-lookup"><span data-stu-id="8aa1a-625">ColumnName</span></span>|<span data-ttu-id="8aa1a-626">DataType</span><span class="sxs-lookup"><span data-stu-id="8aa1a-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8aa1a-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8aa1a-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="8aa1a-628">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-628">String</span></span>|  
|<span data-ttu-id="8aa1a-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8aa1a-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="8aa1a-630">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-630">String</span></span>|  
|<span data-ttu-id="8aa1a-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="8aa1a-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="8aa1a-632">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-632">String</span></span>|  
|<span data-ttu-id="8aa1a-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="8aa1a-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="8aa1a-634">Int16</span><span class="sxs-lookup"><span data-stu-id="8aa1a-634">Int16</span></span>|  
|<span data-ttu-id="8aa1a-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="8aa1a-636">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-636">String</span></span>|  
|<span data-ttu-id="8aa1a-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-637">DESCRIPTION</span></span>|<span data-ttu-id="8aa1a-638">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-638">String</span></span>|  
|<span data-ttu-id="8aa1a-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="8aa1a-639">DATE_CREATED</span></span>|<span data-ttu-id="8aa1a-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="8aa1a-640">DateTime</span></span>|  
|<span data-ttu-id="8aa1a-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="8aa1a-641">DATE_MODIFIED</span></span>|<span data-ttu-id="8aa1a-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="8aa1a-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="8aa1a-643">Vistas</span><span class="sxs-lookup"><span data-stu-id="8aa1a-643">Views</span></span>  
  
|<span data-ttu-id="8aa1a-644">ColumName</span><span class="sxs-lookup"><span data-stu-id="8aa1a-644">ColumnName</span></span>|<span data-ttu-id="8aa1a-645">DataType</span><span class="sxs-lookup"><span data-stu-id="8aa1a-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8aa1a-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8aa1a-646">TABLE_CATALOG</span></span>|<span data-ttu-id="8aa1a-647">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-647">String</span></span>|  
|<span data-ttu-id="8aa1a-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8aa1a-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="8aa1a-649">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-649">String</span></span>|  
|<span data-ttu-id="8aa1a-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8aa1a-650">TABLE_NAME</span></span>|<span data-ttu-id="8aa1a-651">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-651">String</span></span>|  
|<span data-ttu-id="8aa1a-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="8aa1a-653">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-653">String</span></span>|  
|<span data-ttu-id="8aa1a-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-654">CHECK_OPTION</span></span>|<span data-ttu-id="8aa1a-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="8aa1a-655">Boolean</span></span>|  
|<span data-ttu-id="8aa1a-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="8aa1a-656">IS_UPDATABLE</span></span>|<span data-ttu-id="8aa1a-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="8aa1a-657">Boolean</span></span>|  
|<span data-ttu-id="8aa1a-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-658">DESCRIPTION</span></span>|<span data-ttu-id="8aa1a-659">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-659">String</span></span>|  
|<span data-ttu-id="8aa1a-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="8aa1a-660">DATE_CREATED</span></span>|<span data-ttu-id="8aa1a-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="8aa1a-661">DateTime</span></span>|  
|<span data-ttu-id="8aa1a-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="8aa1a-662">DATE_MODIFIED</span></span>|<span data-ttu-id="8aa1a-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="8aa1a-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="8aa1a-664">Índices</span><span class="sxs-lookup"><span data-stu-id="8aa1a-664">Indexes</span></span>  
  
|<span data-ttu-id="8aa1a-665">ColumName</span><span class="sxs-lookup"><span data-stu-id="8aa1a-665">ColumnName</span></span>|<span data-ttu-id="8aa1a-666">DataType</span><span class="sxs-lookup"><span data-stu-id="8aa1a-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="8aa1a-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8aa1a-667">TABLE_CATALOG</span></span>|<span data-ttu-id="8aa1a-668">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-668">String</span></span>|  
|<span data-ttu-id="8aa1a-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8aa1a-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="8aa1a-670">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-670">String</span></span>|  
|<span data-ttu-id="8aa1a-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="8aa1a-671">TABLE_NAME</span></span>|<span data-ttu-id="8aa1a-672">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-672">String</span></span>|  
|<span data-ttu-id="8aa1a-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="8aa1a-673">INDEX_CATALOG</span></span>|<span data-ttu-id="8aa1a-674">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-674">String</span></span>|  
|<span data-ttu-id="8aa1a-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="8aa1a-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="8aa1a-676">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-676">String</span></span>|  
|<span data-ttu-id="8aa1a-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="8aa1a-677">INDEX_NAME</span></span>|<span data-ttu-id="8aa1a-678">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-678">String</span></span>|  
|<span data-ttu-id="8aa1a-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="8aa1a-679">PRIMARY_KEY</span></span>|<span data-ttu-id="8aa1a-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="8aa1a-680">Boolean</span></span>|  
|<span data-ttu-id="8aa1a-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="8aa1a-681">UNIQUE</span></span>|<span data-ttu-id="8aa1a-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="8aa1a-682">Boolean</span></span>|  
|<span data-ttu-id="8aa1a-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="8aa1a-683">CLUSTERED</span></span>|<span data-ttu-id="8aa1a-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="8aa1a-684">Boolean</span></span>|  
|<span data-ttu-id="8aa1a-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="8aa1a-685">TYPE</span></span>|<span data-ttu-id="8aa1a-686">Int32</span><span class="sxs-lookup"><span data-stu-id="8aa1a-686">Int32</span></span>|  
|<span data-ttu-id="8aa1a-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="8aa1a-687">FILL_FACTOR</span></span>|<span data-ttu-id="8aa1a-688">Int32</span><span class="sxs-lookup"><span data-stu-id="8aa1a-688">Int32</span></span>|  
|<span data-ttu-id="8aa1a-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="8aa1a-689">INITIAL_SIZE</span></span>|<span data-ttu-id="8aa1a-690">Int32</span><span class="sxs-lookup"><span data-stu-id="8aa1a-690">Int32</span></span>|  
|<span data-ttu-id="8aa1a-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="8aa1a-691">NULLS</span></span>|<span data-ttu-id="8aa1a-692">Int32</span><span class="sxs-lookup"><span data-stu-id="8aa1a-692">Int32</span></span>|  
|<span data-ttu-id="8aa1a-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="8aa1a-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="8aa1a-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="8aa1a-694">Boolean</span></span>|  
|<span data-ttu-id="8aa1a-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="8aa1a-695">AUTO_UPDATE</span></span>|<span data-ttu-id="8aa1a-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="8aa1a-696">Boolean</span></span>|  
|<span data-ttu-id="8aa1a-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-697">NULL_COLLATION</span></span>|<span data-ttu-id="8aa1a-698">Int32</span><span class="sxs-lookup"><span data-stu-id="8aa1a-698">Int32</span></span>|  
|<span data-ttu-id="8aa1a-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="8aa1a-700">Int64</span><span class="sxs-lookup"><span data-stu-id="8aa1a-700">Int64</span></span>|  
|<span data-ttu-id="8aa1a-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="8aa1a-701">COLUMN_NAME</span></span>|<span data-ttu-id="8aa1a-702">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-702">String</span></span>|  
|<span data-ttu-id="8aa1a-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="8aa1a-703">COLUMN_GUID</span></span>|<span data-ttu-id="8aa1a-704">Guid</span><span class="sxs-lookup"><span data-stu-id="8aa1a-704">Guid</span></span>|  
|<span data-ttu-id="8aa1a-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="8aa1a-705">COLUMN_PROPID</span></span>|<span data-ttu-id="8aa1a-706">Int64</span><span class="sxs-lookup"><span data-stu-id="8aa1a-706">Int64</span></span>|  
|<span data-ttu-id="8aa1a-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-707">COLLATION</span></span>|<span data-ttu-id="8aa1a-708">Int16</span><span class="sxs-lookup"><span data-stu-id="8aa1a-708">Int16</span></span>|  
|<span data-ttu-id="8aa1a-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="8aa1a-709">CARDINALITY</span></span>|<span data-ttu-id="8aa1a-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="8aa1a-710">Decimal</span></span>|  
|<span data-ttu-id="8aa1a-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="8aa1a-711">PAGES</span></span>|<span data-ttu-id="8aa1a-712">Int32</span><span class="sxs-lookup"><span data-stu-id="8aa1a-712">Int32</span></span>|  
|<span data-ttu-id="8aa1a-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="8aa1a-713">FILTER_CONDITION</span></span>|<span data-ttu-id="8aa1a-714">String</span><span class="sxs-lookup"><span data-stu-id="8aa1a-714">String</span></span>|  
|<span data-ttu-id="8aa1a-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="8aa1a-715">INTEGRATED</span></span>|<span data-ttu-id="8aa1a-716">Booleano</span><span class="sxs-lookup"><span data-stu-id="8aa1a-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8aa1a-717">Vea también</span><span class="sxs-lookup"><span data-stu-id="8aa1a-717">See Also</span></span>  
 [<span data-ttu-id="8aa1a-718">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="8aa1a-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
