---
title: Colecciones de esquemas de OLE DB
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: f753f35aab0a0200da5de463a73abb9813253d11
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54658460"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="053d2-102">Colecciones de esquemas de OLE DB</span><span class="sxs-lookup"><span data-stu-id="053d2-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="053d2-103">En esta sección se describe la compatibilidad de las colecciones de esquemas con los proveedores OLE DB de Microsoft SQL Server, Oracle y Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="053d2-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="053d2-104">Proveedor OLE DB para Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="053d2-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="053d2-105">El controlador OLE DB de Microsoft SQL Server admite las siguientes colecciones de esquemas específicas además de las colecciones de esquemas comunes:</span><span class="sxs-lookup"><span data-stu-id="053d2-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="053d2-106">Tablas</span><span class="sxs-lookup"><span data-stu-id="053d2-106">Tables</span></span>  
  
-   <span data-ttu-id="053d2-107">Columnas</span><span class="sxs-lookup"><span data-stu-id="053d2-107">Columns</span></span>  
  
-   <span data-ttu-id="053d2-108">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="053d2-108">Procedures</span></span>  
  
-   <span data-ttu-id="053d2-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="053d2-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="053d2-110">Catálogo</span><span class="sxs-lookup"><span data-stu-id="053d2-110">Catalog</span></span>  
  
-   <span data-ttu-id="053d2-111">Índices</span><span class="sxs-lookup"><span data-stu-id="053d2-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="053d2-112">Tablas</span><span class="sxs-lookup"><span data-stu-id="053d2-112">Tables</span></span>  
  
|<span data-ttu-id="053d2-113">ColumName</span><span class="sxs-lookup"><span data-stu-id="053d2-113">ColumnName</span></span>|<span data-ttu-id="053d2-114">DataType</span><span class="sxs-lookup"><span data-stu-id="053d2-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="053d2-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="053d2-115">TABLE_CATALOG</span></span>|<span data-ttu-id="053d2-116">String</span><span class="sxs-lookup"><span data-stu-id="053d2-116">String</span></span>|  
|<span data-ttu-id="053d2-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="053d2-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="053d2-118">String</span><span class="sxs-lookup"><span data-stu-id="053d2-118">String</span></span>|  
|<span data-ttu-id="053d2-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="053d2-119">TABLE_NAME</span></span>|<span data-ttu-id="053d2-120">String</span><span class="sxs-lookup"><span data-stu-id="053d2-120">String</span></span>|  
|<span data-ttu-id="053d2-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="053d2-121">TABLE_TYPE</span></span>|<span data-ttu-id="053d2-122">String</span><span class="sxs-lookup"><span data-stu-id="053d2-122">String</span></span>|  
|<span data-ttu-id="053d2-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="053d2-123">TABLE_GUID</span></span>|<span data-ttu-id="053d2-124">Guid</span><span class="sxs-lookup"><span data-stu-id="053d2-124">Guid</span></span>|  
|<span data-ttu-id="053d2-125">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="053d2-125">DESCRIPTION</span></span>|<span data-ttu-id="053d2-126">String</span><span class="sxs-lookup"><span data-stu-id="053d2-126">String</span></span>|  
|<span data-ttu-id="053d2-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="053d2-127">TABLE_PROPID</span></span>|<span data-ttu-id="053d2-128">Int64</span><span class="sxs-lookup"><span data-stu-id="053d2-128">Int64</span></span>|  
|<span data-ttu-id="053d2-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="053d2-129">DATE_CREATED</span></span>|<span data-ttu-id="053d2-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="053d2-130">DateTime</span></span>|  
|<span data-ttu-id="053d2-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="053d2-131">DATE_MODIFIED</span></span>|<span data-ttu-id="053d2-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="053d2-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="053d2-133">Columnas</span><span class="sxs-lookup"><span data-stu-id="053d2-133">Columns</span></span>  
  
|<span data-ttu-id="053d2-134">ColumName</span><span class="sxs-lookup"><span data-stu-id="053d2-134">ColumnName</span></span>|<span data-ttu-id="053d2-135">DataType</span><span class="sxs-lookup"><span data-stu-id="053d2-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="053d2-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="053d2-136">TABLE_CATALOG</span></span>|<span data-ttu-id="053d2-137">String</span><span class="sxs-lookup"><span data-stu-id="053d2-137">String</span></span>|  
|<span data-ttu-id="053d2-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="053d2-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="053d2-139">String</span><span class="sxs-lookup"><span data-stu-id="053d2-139">String</span></span>|  
|<span data-ttu-id="053d2-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="053d2-140">TABLE_NAME</span></span>|<span data-ttu-id="053d2-141">String</span><span class="sxs-lookup"><span data-stu-id="053d2-141">String</span></span>|  
|<span data-ttu-id="053d2-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="053d2-142">COLUMN_NAME</span></span>|<span data-ttu-id="053d2-143">String</span><span class="sxs-lookup"><span data-stu-id="053d2-143">String</span></span>|  
|<span data-ttu-id="053d2-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="053d2-144">COLUMN_GUID</span></span>|<span data-ttu-id="053d2-145">Guid</span><span class="sxs-lookup"><span data-stu-id="053d2-145">Guid</span></span>|  
|<span data-ttu-id="053d2-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="053d2-146">COLUMN_PROPID</span></span>|<span data-ttu-id="053d2-147">Int64</span><span class="sxs-lookup"><span data-stu-id="053d2-147">Int64</span></span>|  
|<span data-ttu-id="053d2-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="053d2-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="053d2-149">Int64</span><span class="sxs-lookup"><span data-stu-id="053d2-149">Int64</span></span>|  
|<span data-ttu-id="053d2-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="053d2-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="053d2-151">Boolean</span><span class="sxs-lookup"><span data-stu-id="053d2-151">Boolean</span></span>|  
|<span data-ttu-id="053d2-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="053d2-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="053d2-153">String</span><span class="sxs-lookup"><span data-stu-id="053d2-153">String</span></span>|  
|<span data-ttu-id="053d2-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="053d2-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="053d2-155">Int64</span><span class="sxs-lookup"><span data-stu-id="053d2-155">Int64</span></span>|  
|<span data-ttu-id="053d2-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="053d2-156">IS_NULLABLE</span></span>|<span data-ttu-id="053d2-157">Boolean</span><span class="sxs-lookup"><span data-stu-id="053d2-157">Boolean</span></span>|  
|<span data-ttu-id="053d2-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="053d2-158">DATA_TYPE</span></span>|<span data-ttu-id="053d2-159">Int32</span><span class="sxs-lookup"><span data-stu-id="053d2-159">Int32</span></span>|  
|<span data-ttu-id="053d2-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="053d2-160">TYPE_GUID</span></span>|<span data-ttu-id="053d2-161">Guid</span><span class="sxs-lookup"><span data-stu-id="053d2-161">Guid</span></span>|  
|<span data-ttu-id="053d2-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="053d2-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="053d2-163">Int64</span><span class="sxs-lookup"><span data-stu-id="053d2-163">Int64</span></span>|  
|<span data-ttu-id="053d2-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="053d2-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="053d2-165">Int64</span><span class="sxs-lookup"><span data-stu-id="053d2-165">Int64</span></span>|  
|<span data-ttu-id="053d2-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="053d2-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="053d2-167">Int32</span><span class="sxs-lookup"><span data-stu-id="053d2-167">Int32</span></span>|  
|<span data-ttu-id="053d2-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="053d2-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="053d2-169">Int16</span><span class="sxs-lookup"><span data-stu-id="053d2-169">Int16</span></span>|  
|<span data-ttu-id="053d2-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="053d2-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="053d2-171">Int64</span><span class="sxs-lookup"><span data-stu-id="053d2-171">Int64</span></span>|  
|<span data-ttu-id="053d2-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="053d2-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="053d2-173">String</span><span class="sxs-lookup"><span data-stu-id="053d2-173">String</span></span>|  
|<span data-ttu-id="053d2-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="053d2-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="053d2-175">String</span><span class="sxs-lookup"><span data-stu-id="053d2-175">String</span></span>|  
|<span data-ttu-id="053d2-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="053d2-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="053d2-177">String</span><span class="sxs-lookup"><span data-stu-id="053d2-177">String</span></span>|  
|<span data-ttu-id="053d2-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="053d2-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="053d2-179">String</span><span class="sxs-lookup"><span data-stu-id="053d2-179">String</span></span>|  
|<span data-ttu-id="053d2-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="053d2-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="053d2-181">String</span><span class="sxs-lookup"><span data-stu-id="053d2-181">String</span></span>|  
|<span data-ttu-id="053d2-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="053d2-182">COLLATION_NAME</span></span>|<span data-ttu-id="053d2-183">String</span><span class="sxs-lookup"><span data-stu-id="053d2-183">String</span></span>|  
|<span data-ttu-id="053d2-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="053d2-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="053d2-185">String</span><span class="sxs-lookup"><span data-stu-id="053d2-185">String</span></span>|  
|<span data-ttu-id="053d2-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="053d2-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="053d2-187">String</span><span class="sxs-lookup"><span data-stu-id="053d2-187">String</span></span>|  
|<span data-ttu-id="053d2-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="053d2-188">DOMAIN_NAME</span></span>|<span data-ttu-id="053d2-189">String</span><span class="sxs-lookup"><span data-stu-id="053d2-189">String</span></span>|  
|<span data-ttu-id="053d2-190">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="053d2-190">DESCRIPTION</span></span>|<span data-ttu-id="053d2-191">String</span><span class="sxs-lookup"><span data-stu-id="053d2-191">String</span></span>|  
|<span data-ttu-id="053d2-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="053d2-192">COLUMN_LCID</span></span>|<span data-ttu-id="053d2-193">Int32</span><span class="sxs-lookup"><span data-stu-id="053d2-193">Int32</span></span>|  
|<span data-ttu-id="053d2-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="053d2-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="053d2-195">Int32</span><span class="sxs-lookup"><span data-stu-id="053d2-195">Int32</span></span>|  
|<span data-ttu-id="053d2-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="053d2-196">COLUMN_SORTID</span></span>|<span data-ttu-id="053d2-197">Int32</span><span class="sxs-lookup"><span data-stu-id="053d2-197">Int32</span></span>|  
|<span data-ttu-id="053d2-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="053d2-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="053d2-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="053d2-199">Byte[]</span></span>|  
|<span data-ttu-id="053d2-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="053d2-200">IS_COMPUTED</span></span>|<span data-ttu-id="053d2-201">Boolean</span><span class="sxs-lookup"><span data-stu-id="053d2-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="053d2-202">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="053d2-202">Procedures</span></span>  
  
|<span data-ttu-id="053d2-203">ColumName</span><span class="sxs-lookup"><span data-stu-id="053d2-203">ColumnName</span></span>|<span data-ttu-id="053d2-204">DataType</span><span class="sxs-lookup"><span data-stu-id="053d2-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="053d2-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="053d2-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="053d2-206">String</span><span class="sxs-lookup"><span data-stu-id="053d2-206">String</span></span>|  
|<span data-ttu-id="053d2-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="053d2-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="053d2-208">String</span><span class="sxs-lookup"><span data-stu-id="053d2-208">String</span></span>|  
|<span data-ttu-id="053d2-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="053d2-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="053d2-210">String</span><span class="sxs-lookup"><span data-stu-id="053d2-210">String</span></span>|  
|<span data-ttu-id="053d2-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="053d2-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="053d2-212">Int16</span><span class="sxs-lookup"><span data-stu-id="053d2-212">Int16</span></span>|  
|<span data-ttu-id="053d2-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="053d2-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="053d2-214">String</span><span class="sxs-lookup"><span data-stu-id="053d2-214">String</span></span>|  
|<span data-ttu-id="053d2-215">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="053d2-215">DESCRIPTION</span></span>|<span data-ttu-id="053d2-216">String</span><span class="sxs-lookup"><span data-stu-id="053d2-216">String</span></span>|  
|<span data-ttu-id="053d2-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="053d2-217">DATE_CREATED</span></span>|<span data-ttu-id="053d2-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="053d2-218">DateTime</span></span>|  
|<span data-ttu-id="053d2-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="053d2-219">DATE_MODIFIED</span></span>|<span data-ttu-id="053d2-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="053d2-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="053d2-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="053d2-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="053d2-222">ColumName</span><span class="sxs-lookup"><span data-stu-id="053d2-222">ColumnName</span></span>|<span data-ttu-id="053d2-223">DataType</span><span class="sxs-lookup"><span data-stu-id="053d2-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="053d2-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="053d2-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="053d2-225">String</span><span class="sxs-lookup"><span data-stu-id="053d2-225">String</span></span>|  
|<span data-ttu-id="053d2-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="053d2-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="053d2-227">String</span><span class="sxs-lookup"><span data-stu-id="053d2-227">String</span></span>|  
|<span data-ttu-id="053d2-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="053d2-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="053d2-229">String</span><span class="sxs-lookup"><span data-stu-id="053d2-229">String</span></span>|  
|<span data-ttu-id="053d2-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="053d2-230">PARAMETER_NAME</span></span>|<span data-ttu-id="053d2-231">String</span><span class="sxs-lookup"><span data-stu-id="053d2-231">String</span></span>|  
|<span data-ttu-id="053d2-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="053d2-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="053d2-233">Int32</span><span class="sxs-lookup"><span data-stu-id="053d2-233">Int32</span></span>|  
|<span data-ttu-id="053d2-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="053d2-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="053d2-235">Int32</span><span class="sxs-lookup"><span data-stu-id="053d2-235">Int32</span></span>|  
|<span data-ttu-id="053d2-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="053d2-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="053d2-237">Boolean</span><span class="sxs-lookup"><span data-stu-id="053d2-237">Boolean</span></span>|  
|<span data-ttu-id="053d2-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="053d2-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="053d2-239">String</span><span class="sxs-lookup"><span data-stu-id="053d2-239">String</span></span>|  
|<span data-ttu-id="053d2-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="053d2-240">IS_NULLABLE</span></span>|<span data-ttu-id="053d2-241">Boolean</span><span class="sxs-lookup"><span data-stu-id="053d2-241">Boolean</span></span>|  
|<span data-ttu-id="053d2-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="053d2-242">DATA_TYPE</span></span>|<span data-ttu-id="053d2-243">Int32</span><span class="sxs-lookup"><span data-stu-id="053d2-243">Int32</span></span>|  
|<span data-ttu-id="053d2-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="053d2-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="053d2-245">Int64</span><span class="sxs-lookup"><span data-stu-id="053d2-245">Int64</span></span>|  
|<span data-ttu-id="053d2-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="053d2-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="053d2-247">Int64</span><span class="sxs-lookup"><span data-stu-id="053d2-247">Int64</span></span>|  
|<span data-ttu-id="053d2-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="053d2-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="053d2-249">Int32</span><span class="sxs-lookup"><span data-stu-id="053d2-249">Int32</span></span>|  
|<span data-ttu-id="053d2-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="053d2-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="053d2-251">Int16</span><span class="sxs-lookup"><span data-stu-id="053d2-251">Int16</span></span>|  
|<span data-ttu-id="053d2-252">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="053d2-252">DESCRIPTION</span></span>|<span data-ttu-id="053d2-253">String</span><span class="sxs-lookup"><span data-stu-id="053d2-253">String</span></span>|  
|<span data-ttu-id="053d2-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="053d2-254">TYPE_NAME</span></span>|<span data-ttu-id="053d2-255">String</span><span class="sxs-lookup"><span data-stu-id="053d2-255">String</span></span>|  
|<span data-ttu-id="053d2-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="053d2-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="053d2-257">String</span><span class="sxs-lookup"><span data-stu-id="053d2-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="053d2-258">Catálogo</span><span class="sxs-lookup"><span data-stu-id="053d2-258">Catalog</span></span>  
  
|<span data-ttu-id="053d2-259">ColumName</span><span class="sxs-lookup"><span data-stu-id="053d2-259">ColumnName</span></span>|<span data-ttu-id="053d2-260">DataType</span><span class="sxs-lookup"><span data-stu-id="053d2-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="053d2-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="053d2-261">CATALOG_NAME</span></span>|<span data-ttu-id="053d2-262">String</span><span class="sxs-lookup"><span data-stu-id="053d2-262">String</span></span>|  
|<span data-ttu-id="053d2-263">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="053d2-263">DESCRIPTION</span></span>|<span data-ttu-id="053d2-264">String</span><span class="sxs-lookup"><span data-stu-id="053d2-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="053d2-265">Índices</span><span class="sxs-lookup"><span data-stu-id="053d2-265">Indexes</span></span>  
  
|<span data-ttu-id="053d2-266">ColumName</span><span class="sxs-lookup"><span data-stu-id="053d2-266">ColumnName</span></span>|<span data-ttu-id="053d2-267">DataType</span><span class="sxs-lookup"><span data-stu-id="053d2-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="053d2-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="053d2-268">TABLE_CATALOG</span></span>|<span data-ttu-id="053d2-269">String</span><span class="sxs-lookup"><span data-stu-id="053d2-269">String</span></span>|  
|<span data-ttu-id="053d2-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="053d2-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="053d2-271">String</span><span class="sxs-lookup"><span data-stu-id="053d2-271">String</span></span>|  
|<span data-ttu-id="053d2-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="053d2-272">TABLE_NAME</span></span>|<span data-ttu-id="053d2-273">String</span><span class="sxs-lookup"><span data-stu-id="053d2-273">String</span></span>|  
|<span data-ttu-id="053d2-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="053d2-274">INDEX_CATALOG</span></span>|<span data-ttu-id="053d2-275">String</span><span class="sxs-lookup"><span data-stu-id="053d2-275">String</span></span>|  
|<span data-ttu-id="053d2-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="053d2-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="053d2-277">String</span><span class="sxs-lookup"><span data-stu-id="053d2-277">String</span></span>|  
|<span data-ttu-id="053d2-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="053d2-278">INDEX_NAME</span></span>|<span data-ttu-id="053d2-279">String</span><span class="sxs-lookup"><span data-stu-id="053d2-279">String</span></span>|  
|<span data-ttu-id="053d2-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="053d2-280">PRIMARY_KEY</span></span>|<span data-ttu-id="053d2-281">Boolean</span><span class="sxs-lookup"><span data-stu-id="053d2-281">Boolean</span></span>|  
|<span data-ttu-id="053d2-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="053d2-282">UNIQUE</span></span>|<span data-ttu-id="053d2-283">Boolean</span><span class="sxs-lookup"><span data-stu-id="053d2-283">Boolean</span></span>|  
|<span data-ttu-id="053d2-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="053d2-284">CLUSTERED</span></span>|<span data-ttu-id="053d2-285">Boolean</span><span class="sxs-lookup"><span data-stu-id="053d2-285">Boolean</span></span>|  
|<span data-ttu-id="053d2-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="053d2-286">TYPE</span></span>|<span data-ttu-id="053d2-287">Int32</span><span class="sxs-lookup"><span data-stu-id="053d2-287">Int32</span></span>|  
|<span data-ttu-id="053d2-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="053d2-288">FILL_FACTOR</span></span>|<span data-ttu-id="053d2-289">Int32</span><span class="sxs-lookup"><span data-stu-id="053d2-289">Int32</span></span>|  
|<span data-ttu-id="053d2-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="053d2-290">INITIAL_SIZE</span></span>|<span data-ttu-id="053d2-291">Int32</span><span class="sxs-lookup"><span data-stu-id="053d2-291">Int32</span></span>|  
|<span data-ttu-id="053d2-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="053d2-292">NULLS</span></span>|<span data-ttu-id="053d2-293">Int32</span><span class="sxs-lookup"><span data-stu-id="053d2-293">Int32</span></span>|  
|<span data-ttu-id="053d2-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="053d2-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="053d2-295">Boolean</span><span class="sxs-lookup"><span data-stu-id="053d2-295">Boolean</span></span>|  
|<span data-ttu-id="053d2-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="053d2-296">AUTO_UPDATE</span></span>|<span data-ttu-id="053d2-297">Boolean</span><span class="sxs-lookup"><span data-stu-id="053d2-297">Boolean</span></span>|  
|<span data-ttu-id="053d2-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="053d2-298">NULL_COLLATION</span></span>|<span data-ttu-id="053d2-299">Int32</span><span class="sxs-lookup"><span data-stu-id="053d2-299">Int32</span></span>|  
|<span data-ttu-id="053d2-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="053d2-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="053d2-301">Int64</span><span class="sxs-lookup"><span data-stu-id="053d2-301">Int64</span></span>|  
|<span data-ttu-id="053d2-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="053d2-302">COLUMN_NAME</span></span>|<span data-ttu-id="053d2-303">String</span><span class="sxs-lookup"><span data-stu-id="053d2-303">String</span></span>|  
|<span data-ttu-id="053d2-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="053d2-304">COLUMN_GUID</span></span>|<span data-ttu-id="053d2-305">Guid</span><span class="sxs-lookup"><span data-stu-id="053d2-305">Guid</span></span>|  
|<span data-ttu-id="053d2-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="053d2-306">COLUMN_PROPID</span></span>|<span data-ttu-id="053d2-307">Int64</span><span class="sxs-lookup"><span data-stu-id="053d2-307">Int64</span></span>|  
|<span data-ttu-id="053d2-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="053d2-308">COLLATION</span></span>|<span data-ttu-id="053d2-309">Int16</span><span class="sxs-lookup"><span data-stu-id="053d2-309">Int16</span></span>|  
|<span data-ttu-id="053d2-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="053d2-310">CARDINALITY</span></span>|<span data-ttu-id="053d2-311">Decimal</span><span class="sxs-lookup"><span data-stu-id="053d2-311">Decimal</span></span>|  
|<span data-ttu-id="053d2-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="053d2-312">PAGES</span></span>|<span data-ttu-id="053d2-313">Int32</span><span class="sxs-lookup"><span data-stu-id="053d2-313">Int32</span></span>|  
|<span data-ttu-id="053d2-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="053d2-314">FILTER_CONDITION</span></span>|<span data-ttu-id="053d2-315">String</span><span class="sxs-lookup"><span data-stu-id="053d2-315">String</span></span>|  
|<span data-ttu-id="053d2-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="053d2-316">INTEGRATED</span></span>|<span data-ttu-id="053d2-317">Boolean</span><span class="sxs-lookup"><span data-stu-id="053d2-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="053d2-318">Proveedor OLE DB de Microsoft para Oracle</span><span class="sxs-lookup"><span data-stu-id="053d2-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="053d2-319">El controlador OLE DB de Microsoft para Oracle admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="053d2-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="053d2-320">Tablas</span><span class="sxs-lookup"><span data-stu-id="053d2-320">Tables</span></span>  
  
-   <span data-ttu-id="053d2-321">Columnas</span><span class="sxs-lookup"><span data-stu-id="053d2-321">Columns</span></span>  
  
-   <span data-ttu-id="053d2-322">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="053d2-322">Procedures</span></span>  
  
-   <span data-ttu-id="053d2-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="053d2-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="053d2-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="053d2-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="053d2-325">Vistas</span><span class="sxs-lookup"><span data-stu-id="053d2-325">Views</span></span>  
  
-   <span data-ttu-id="053d2-326">Índices</span><span class="sxs-lookup"><span data-stu-id="053d2-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="053d2-327">Tablas</span><span class="sxs-lookup"><span data-stu-id="053d2-327">Tables</span></span>  
  
|<span data-ttu-id="053d2-328">ColumName</span><span class="sxs-lookup"><span data-stu-id="053d2-328">ColumnName</span></span>|<span data-ttu-id="053d2-329">DataType</span><span class="sxs-lookup"><span data-stu-id="053d2-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="053d2-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="053d2-330">TABLE_CATALOG</span></span>|<span data-ttu-id="053d2-331">String</span><span class="sxs-lookup"><span data-stu-id="053d2-331">String</span></span>|  
|<span data-ttu-id="053d2-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="053d2-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="053d2-333">String</span><span class="sxs-lookup"><span data-stu-id="053d2-333">String</span></span>|  
|<span data-ttu-id="053d2-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="053d2-334">TABLE_NAME</span></span>|<span data-ttu-id="053d2-335">String</span><span class="sxs-lookup"><span data-stu-id="053d2-335">String</span></span>|  
|<span data-ttu-id="053d2-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="053d2-336">TABLE_TYPE</span></span>|<span data-ttu-id="053d2-337">String</span><span class="sxs-lookup"><span data-stu-id="053d2-337">String</span></span>|  
|<span data-ttu-id="053d2-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="053d2-338">TABLE_GUID</span></span>|<span data-ttu-id="053d2-339">Guid</span><span class="sxs-lookup"><span data-stu-id="053d2-339">Guid</span></span>|  
|<span data-ttu-id="053d2-340">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="053d2-340">DESCRIPTION</span></span>|<span data-ttu-id="053d2-341">String</span><span class="sxs-lookup"><span data-stu-id="053d2-341">String</span></span>|  
|<span data-ttu-id="053d2-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="053d2-342">TABLE_PROPID</span></span>|<span data-ttu-id="053d2-343">Int64</span><span class="sxs-lookup"><span data-stu-id="053d2-343">Int64</span></span>|  
|<span data-ttu-id="053d2-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="053d2-344">DATE_CREATED</span></span>|<span data-ttu-id="053d2-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="053d2-345">DateTime</span></span>|  
|<span data-ttu-id="053d2-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="053d2-346">DATE_MODIFIED</span></span>|<span data-ttu-id="053d2-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="053d2-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="053d2-348">Columnas</span><span class="sxs-lookup"><span data-stu-id="053d2-348">Columns</span></span>  
  
|<span data-ttu-id="053d2-349">ColumName</span><span class="sxs-lookup"><span data-stu-id="053d2-349">ColumnName</span></span>|<span data-ttu-id="053d2-350">DataType</span><span class="sxs-lookup"><span data-stu-id="053d2-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="053d2-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="053d2-351">TABLE_CATALOG</span></span>|<span data-ttu-id="053d2-352">String</span><span class="sxs-lookup"><span data-stu-id="053d2-352">String</span></span>|  
|<span data-ttu-id="053d2-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="053d2-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="053d2-354">String</span><span class="sxs-lookup"><span data-stu-id="053d2-354">String</span></span>|  
|<span data-ttu-id="053d2-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="053d2-355">TABLE_NAME</span></span>|<span data-ttu-id="053d2-356">String</span><span class="sxs-lookup"><span data-stu-id="053d2-356">String</span></span>|  
|<span data-ttu-id="053d2-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="053d2-357">COLUMN_NAME</span></span>|<span data-ttu-id="053d2-358">String</span><span class="sxs-lookup"><span data-stu-id="053d2-358">String</span></span>|  
|<span data-ttu-id="053d2-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="053d2-359">COLUMN_GUID</span></span>|<span data-ttu-id="053d2-360">Guid</span><span class="sxs-lookup"><span data-stu-id="053d2-360">Guid</span></span>|  
|<span data-ttu-id="053d2-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="053d2-361">COLUMN_PROPID</span></span>|<span data-ttu-id="053d2-362">Int64</span><span class="sxs-lookup"><span data-stu-id="053d2-362">Int64</span></span>|  
|<span data-ttu-id="053d2-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="053d2-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="053d2-364">Int64</span><span class="sxs-lookup"><span data-stu-id="053d2-364">Int64</span></span>|  
|<span data-ttu-id="053d2-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="053d2-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="053d2-366">Boolean</span><span class="sxs-lookup"><span data-stu-id="053d2-366">Boolean</span></span>|  
|<span data-ttu-id="053d2-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="053d2-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="053d2-368">String</span><span class="sxs-lookup"><span data-stu-id="053d2-368">String</span></span>|  
|<span data-ttu-id="053d2-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="053d2-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="053d2-370">Int64</span><span class="sxs-lookup"><span data-stu-id="053d2-370">Int64</span></span>|  
|<span data-ttu-id="053d2-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="053d2-371">IS_NULLABLE</span></span>|<span data-ttu-id="053d2-372">Boolean</span><span class="sxs-lookup"><span data-stu-id="053d2-372">Boolean</span></span>|  
|<span data-ttu-id="053d2-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="053d2-373">DATA_TYPE</span></span>|<span data-ttu-id="053d2-374">Int32</span><span class="sxs-lookup"><span data-stu-id="053d2-374">Int32</span></span>|  
|<span data-ttu-id="053d2-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="053d2-375">TYPE_GUID</span></span>|<span data-ttu-id="053d2-376">Guid</span><span class="sxs-lookup"><span data-stu-id="053d2-376">Guid</span></span>|  
|<span data-ttu-id="053d2-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="053d2-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="053d2-378">Int64</span><span class="sxs-lookup"><span data-stu-id="053d2-378">Int64</span></span>|  
|<span data-ttu-id="053d2-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="053d2-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="053d2-380">Int64</span><span class="sxs-lookup"><span data-stu-id="053d2-380">Int64</span></span>|  
|<span data-ttu-id="053d2-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="053d2-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="053d2-382">Int32</span><span class="sxs-lookup"><span data-stu-id="053d2-382">Int32</span></span>|  
|<span data-ttu-id="053d2-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="053d2-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="053d2-384">Int16</span><span class="sxs-lookup"><span data-stu-id="053d2-384">Int16</span></span>|  
|<span data-ttu-id="053d2-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="053d2-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="053d2-386">Int64</span><span class="sxs-lookup"><span data-stu-id="053d2-386">Int64</span></span>|  
|<span data-ttu-id="053d2-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="053d2-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="053d2-388">String</span><span class="sxs-lookup"><span data-stu-id="053d2-388">String</span></span>|  
|<span data-ttu-id="053d2-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="053d2-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="053d2-390">String</span><span class="sxs-lookup"><span data-stu-id="053d2-390">String</span></span>|  
|<span data-ttu-id="053d2-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="053d2-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="053d2-392">String</span><span class="sxs-lookup"><span data-stu-id="053d2-392">String</span></span>|  
|<span data-ttu-id="053d2-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="053d2-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="053d2-394">String</span><span class="sxs-lookup"><span data-stu-id="053d2-394">String</span></span>|  
|<span data-ttu-id="053d2-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="053d2-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="053d2-396">String</span><span class="sxs-lookup"><span data-stu-id="053d2-396">String</span></span>|  
|<span data-ttu-id="053d2-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="053d2-397">COLLATION_NAME</span></span>|<span data-ttu-id="053d2-398">String</span><span class="sxs-lookup"><span data-stu-id="053d2-398">String</span></span>|  
|<span data-ttu-id="053d2-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="053d2-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="053d2-400">String</span><span class="sxs-lookup"><span data-stu-id="053d2-400">String</span></span>|  
|<span data-ttu-id="053d2-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="053d2-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="053d2-402">String</span><span class="sxs-lookup"><span data-stu-id="053d2-402">String</span></span>|  
|<span data-ttu-id="053d2-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="053d2-403">DOMAIN_NAME</span></span>|<span data-ttu-id="053d2-404">String</span><span class="sxs-lookup"><span data-stu-id="053d2-404">String</span></span>|  
|<span data-ttu-id="053d2-405">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="053d2-405">DESCRIPTION</span></span>|<span data-ttu-id="053d2-406">String</span><span class="sxs-lookup"><span data-stu-id="053d2-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="053d2-407">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="053d2-407">Procedures</span></span>  
  
|<span data-ttu-id="053d2-408">ColumName</span><span class="sxs-lookup"><span data-stu-id="053d2-408">ColumnName</span></span>|<span data-ttu-id="053d2-409">DataType</span><span class="sxs-lookup"><span data-stu-id="053d2-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="053d2-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="053d2-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="053d2-411">String</span><span class="sxs-lookup"><span data-stu-id="053d2-411">String</span></span>|  
|<span data-ttu-id="053d2-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="053d2-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="053d2-413">String</span><span class="sxs-lookup"><span data-stu-id="053d2-413">String</span></span>|  
|<span data-ttu-id="053d2-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="053d2-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="053d2-415">String</span><span class="sxs-lookup"><span data-stu-id="053d2-415">String</span></span>|  
|<span data-ttu-id="053d2-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="053d2-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="053d2-417">Int16</span><span class="sxs-lookup"><span data-stu-id="053d2-417">Int16</span></span>|  
|<span data-ttu-id="053d2-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="053d2-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="053d2-419">String</span><span class="sxs-lookup"><span data-stu-id="053d2-419">String</span></span>|  
|<span data-ttu-id="053d2-420">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="053d2-420">DESCRIPTION</span></span>|<span data-ttu-id="053d2-421">String</span><span class="sxs-lookup"><span data-stu-id="053d2-421">String</span></span>|  
|<span data-ttu-id="053d2-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="053d2-422">DATE_CREATED</span></span>|<span data-ttu-id="053d2-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="053d2-423">DateTime</span></span>|  
|<span data-ttu-id="053d2-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="053d2-424">DATE_MODIFIED</span></span>|<span data-ttu-id="053d2-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="053d2-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="053d2-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="053d2-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="053d2-427">ColumName</span><span class="sxs-lookup"><span data-stu-id="053d2-427">ColumnName</span></span>|<span data-ttu-id="053d2-428">DataType</span><span class="sxs-lookup"><span data-stu-id="053d2-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="053d2-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="053d2-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="053d2-430">String</span><span class="sxs-lookup"><span data-stu-id="053d2-430">String</span></span>|  
|<span data-ttu-id="053d2-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="053d2-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="053d2-432">String</span><span class="sxs-lookup"><span data-stu-id="053d2-432">String</span></span>|  
|<span data-ttu-id="053d2-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="053d2-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="053d2-434">String</span><span class="sxs-lookup"><span data-stu-id="053d2-434">String</span></span>|  
|<span data-ttu-id="053d2-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="053d2-435">COLUMN_NAME</span></span>|<span data-ttu-id="053d2-436">String</span><span class="sxs-lookup"><span data-stu-id="053d2-436">String</span></span>|  
|<span data-ttu-id="053d2-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="053d2-437">COLUMN_GUID</span></span>|<span data-ttu-id="053d2-438">Guid</span><span class="sxs-lookup"><span data-stu-id="053d2-438">Guid</span></span>|  
|<span data-ttu-id="053d2-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="053d2-439">COLUMN_PROPID</span></span>|<span data-ttu-id="053d2-440">Int64</span><span class="sxs-lookup"><span data-stu-id="053d2-440">Int64</span></span>|  
|<span data-ttu-id="053d2-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="053d2-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="053d2-442">Int64</span><span class="sxs-lookup"><span data-stu-id="053d2-442">Int64</span></span>|  
|<span data-ttu-id="053d2-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="053d2-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="053d2-444">Int64</span><span class="sxs-lookup"><span data-stu-id="053d2-444">Int64</span></span>|  
|<span data-ttu-id="053d2-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="053d2-445">IS_NULLABLE</span></span>|<span data-ttu-id="053d2-446">Boolean</span><span class="sxs-lookup"><span data-stu-id="053d2-446">Boolean</span></span>|  
|<span data-ttu-id="053d2-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="053d2-447">DATA_TYPE</span></span>|<span data-ttu-id="053d2-448">Int32</span><span class="sxs-lookup"><span data-stu-id="053d2-448">Int32</span></span>|  
|<span data-ttu-id="053d2-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="053d2-449">TYPE_GUID</span></span>|<span data-ttu-id="053d2-450">Guid</span><span class="sxs-lookup"><span data-stu-id="053d2-450">Guid</span></span>|  
|<span data-ttu-id="053d2-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="053d2-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="053d2-452">Int64</span><span class="sxs-lookup"><span data-stu-id="053d2-452">Int64</span></span>|  
|<span data-ttu-id="053d2-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="053d2-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="053d2-454">Int64</span><span class="sxs-lookup"><span data-stu-id="053d2-454">Int64</span></span>|  
|<span data-ttu-id="053d2-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="053d2-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="053d2-456">Int32</span><span class="sxs-lookup"><span data-stu-id="053d2-456">Int32</span></span>|  
|<span data-ttu-id="053d2-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="053d2-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="053d2-458">Int16</span><span class="sxs-lookup"><span data-stu-id="053d2-458">Int16</span></span>|  
|<span data-ttu-id="053d2-459">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="053d2-459">DESCRIPTION</span></span>|<span data-ttu-id="053d2-460">String</span><span class="sxs-lookup"><span data-stu-id="053d2-460">String</span></span>|  
|<span data-ttu-id="053d2-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="053d2-461">OVERLOAD</span></span>|<span data-ttu-id="053d2-462">Int16</span><span class="sxs-lookup"><span data-stu-id="053d2-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="053d2-463">Vistas</span><span class="sxs-lookup"><span data-stu-id="053d2-463">Views</span></span>  
  
|<span data-ttu-id="053d2-464">ColumName</span><span class="sxs-lookup"><span data-stu-id="053d2-464">ColumnName</span></span>|<span data-ttu-id="053d2-465">DataType</span><span class="sxs-lookup"><span data-stu-id="053d2-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="053d2-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="053d2-466">TABLE_CATALOG</span></span>|<span data-ttu-id="053d2-467">String</span><span class="sxs-lookup"><span data-stu-id="053d2-467">String</span></span>|  
|<span data-ttu-id="053d2-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="053d2-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="053d2-469">String</span><span class="sxs-lookup"><span data-stu-id="053d2-469">String</span></span>|  
|<span data-ttu-id="053d2-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="053d2-470">TABLE_NAME</span></span>|<span data-ttu-id="053d2-471">String</span><span class="sxs-lookup"><span data-stu-id="053d2-471">String</span></span>|  
|<span data-ttu-id="053d2-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="053d2-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="053d2-473">String</span><span class="sxs-lookup"><span data-stu-id="053d2-473">String</span></span>|  
|<span data-ttu-id="053d2-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="053d2-474">CHECK_OPTION</span></span>|<span data-ttu-id="053d2-475">Boolean</span><span class="sxs-lookup"><span data-stu-id="053d2-475">Boolean</span></span>|  
|<span data-ttu-id="053d2-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="053d2-476">IS_UPDATABLE</span></span>|<span data-ttu-id="053d2-477">Boolean</span><span class="sxs-lookup"><span data-stu-id="053d2-477">Boolean</span></span>|  
|<span data-ttu-id="053d2-478">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="053d2-478">DESCRIPTION</span></span>|<span data-ttu-id="053d2-479">String</span><span class="sxs-lookup"><span data-stu-id="053d2-479">String</span></span>|  
|<span data-ttu-id="053d2-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="053d2-480">DATE_CREATED</span></span>|<span data-ttu-id="053d2-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="053d2-481">DateTime</span></span>|  
|<span data-ttu-id="053d2-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="053d2-482">DATE_MODIFIED</span></span>|<span data-ttu-id="053d2-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="053d2-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="053d2-484">Índices</span><span class="sxs-lookup"><span data-stu-id="053d2-484">Indexes</span></span>  
  
|<span data-ttu-id="053d2-485">ColumName</span><span class="sxs-lookup"><span data-stu-id="053d2-485">ColumnName</span></span>|<span data-ttu-id="053d2-486">DataType</span><span class="sxs-lookup"><span data-stu-id="053d2-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="053d2-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="053d2-487">TABLE_CATALOG</span></span>|<span data-ttu-id="053d2-488">String</span><span class="sxs-lookup"><span data-stu-id="053d2-488">String</span></span>|  
|<span data-ttu-id="053d2-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="053d2-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="053d2-490">String</span><span class="sxs-lookup"><span data-stu-id="053d2-490">String</span></span>|  
|<span data-ttu-id="053d2-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="053d2-491">TABLE_NAME</span></span>|<span data-ttu-id="053d2-492">String</span><span class="sxs-lookup"><span data-stu-id="053d2-492">String</span></span>|  
|<span data-ttu-id="053d2-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="053d2-493">INDEX_CATALOG</span></span>|<span data-ttu-id="053d2-494">String</span><span class="sxs-lookup"><span data-stu-id="053d2-494">String</span></span>|  
|<span data-ttu-id="053d2-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="053d2-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="053d2-496">String</span><span class="sxs-lookup"><span data-stu-id="053d2-496">String</span></span>|  
|<span data-ttu-id="053d2-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="053d2-497">INDEX_NAME</span></span>|<span data-ttu-id="053d2-498">String</span><span class="sxs-lookup"><span data-stu-id="053d2-498">String</span></span>|  
|<span data-ttu-id="053d2-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="053d2-499">PRIMARY_KEY</span></span>|<span data-ttu-id="053d2-500">Boolean</span><span class="sxs-lookup"><span data-stu-id="053d2-500">Boolean</span></span>|  
|<span data-ttu-id="053d2-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="053d2-501">UNIQUE</span></span>|<span data-ttu-id="053d2-502">Boolean</span><span class="sxs-lookup"><span data-stu-id="053d2-502">Boolean</span></span>|  
|<span data-ttu-id="053d2-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="053d2-503">CLUSTERED</span></span>|<span data-ttu-id="053d2-504">Boolean</span><span class="sxs-lookup"><span data-stu-id="053d2-504">Boolean</span></span>|  
|<span data-ttu-id="053d2-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="053d2-505">TYPE</span></span>|<span data-ttu-id="053d2-506">Int32</span><span class="sxs-lookup"><span data-stu-id="053d2-506">Int32</span></span>|  
|<span data-ttu-id="053d2-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="053d2-507">FILL_FACTOR</span></span>|<span data-ttu-id="053d2-508">Int32</span><span class="sxs-lookup"><span data-stu-id="053d2-508">Int32</span></span>|  
|<span data-ttu-id="053d2-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="053d2-509">INITIAL_SIZE</span></span>|<span data-ttu-id="053d2-510">Int32</span><span class="sxs-lookup"><span data-stu-id="053d2-510">Int32</span></span>|  
|<span data-ttu-id="053d2-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="053d2-511">NULLS</span></span>|<span data-ttu-id="053d2-512">Int32</span><span class="sxs-lookup"><span data-stu-id="053d2-512">Int32</span></span>|  
|<span data-ttu-id="053d2-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="053d2-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="053d2-514">Boolean</span><span class="sxs-lookup"><span data-stu-id="053d2-514">Boolean</span></span>|  
|<span data-ttu-id="053d2-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="053d2-515">AUTO_UPDATE</span></span>|<span data-ttu-id="053d2-516">Boolean</span><span class="sxs-lookup"><span data-stu-id="053d2-516">Boolean</span></span>|  
|<span data-ttu-id="053d2-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="053d2-517">NULL_COLLATION</span></span>|<span data-ttu-id="053d2-518">Int32</span><span class="sxs-lookup"><span data-stu-id="053d2-518">Int32</span></span>|  
|<span data-ttu-id="053d2-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="053d2-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="053d2-520">Int64</span><span class="sxs-lookup"><span data-stu-id="053d2-520">Int64</span></span>|  
|<span data-ttu-id="053d2-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="053d2-521">COLUMN_NAME</span></span>|<span data-ttu-id="053d2-522">String</span><span class="sxs-lookup"><span data-stu-id="053d2-522">String</span></span>|  
|<span data-ttu-id="053d2-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="053d2-523">COLUMN_GUID</span></span>|<span data-ttu-id="053d2-524">Guid</span><span class="sxs-lookup"><span data-stu-id="053d2-524">Guid</span></span>|  
|<span data-ttu-id="053d2-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="053d2-525">COLUMN_PROPID</span></span>|<span data-ttu-id="053d2-526">Int64</span><span class="sxs-lookup"><span data-stu-id="053d2-526">Int64</span></span>|  
|<span data-ttu-id="053d2-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="053d2-527">COLLATION</span></span>|<span data-ttu-id="053d2-528">Int16</span><span class="sxs-lookup"><span data-stu-id="053d2-528">Int16</span></span>|  
|<span data-ttu-id="053d2-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="053d2-529">CARDINALITY</span></span>|<span data-ttu-id="053d2-530">Decimal</span><span class="sxs-lookup"><span data-stu-id="053d2-530">Decimal</span></span>|  
|<span data-ttu-id="053d2-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="053d2-531">PAGES</span></span>|<span data-ttu-id="053d2-532">Int32</span><span class="sxs-lookup"><span data-stu-id="053d2-532">Int32</span></span>|  
|<span data-ttu-id="053d2-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="053d2-533">FILTER_CONDITION</span></span>|<span data-ttu-id="053d2-534">String</span><span class="sxs-lookup"><span data-stu-id="053d2-534">String</span></span>|  
|<span data-ttu-id="053d2-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="053d2-535">INTEGRATED</span></span>|<span data-ttu-id="053d2-536">Boolean</span><span class="sxs-lookup"><span data-stu-id="053d2-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="053d2-537">Proveedor OLE DB de Microsoft para Jet</span><span class="sxs-lookup"><span data-stu-id="053d2-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="053d2-538">El controlador OLE DB de Microsoft para Jet admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="053d2-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="053d2-539">Tablas</span><span class="sxs-lookup"><span data-stu-id="053d2-539">Tables</span></span>  
  
-   <span data-ttu-id="053d2-540">Columnas</span><span class="sxs-lookup"><span data-stu-id="053d2-540">Columns</span></span>  
  
-   <span data-ttu-id="053d2-541">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="053d2-541">Procedures</span></span>  
  
-   <span data-ttu-id="053d2-542">Vistas</span><span class="sxs-lookup"><span data-stu-id="053d2-542">Views</span></span>  
  
-   <span data-ttu-id="053d2-543">Índices</span><span class="sxs-lookup"><span data-stu-id="053d2-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="053d2-544">Tablas</span><span class="sxs-lookup"><span data-stu-id="053d2-544">Tables</span></span>  
  
|<span data-ttu-id="053d2-545">ColumName</span><span class="sxs-lookup"><span data-stu-id="053d2-545">ColumnName</span></span>|<span data-ttu-id="053d2-546">DataType</span><span class="sxs-lookup"><span data-stu-id="053d2-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="053d2-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="053d2-547">TABLE_CATALOG</span></span>|<span data-ttu-id="053d2-548">String</span><span class="sxs-lookup"><span data-stu-id="053d2-548">String</span></span>|  
|<span data-ttu-id="053d2-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="053d2-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="053d2-550">String</span><span class="sxs-lookup"><span data-stu-id="053d2-550">String</span></span>|  
|<span data-ttu-id="053d2-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="053d2-551">TABLE_NAME</span></span>|<span data-ttu-id="053d2-552">String</span><span class="sxs-lookup"><span data-stu-id="053d2-552">String</span></span>|  
|<span data-ttu-id="053d2-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="053d2-553">TABLE_TYPE</span></span>|<span data-ttu-id="053d2-554">String</span><span class="sxs-lookup"><span data-stu-id="053d2-554">String</span></span>|  
|<span data-ttu-id="053d2-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="053d2-555">TABLE_GUID</span></span>|<span data-ttu-id="053d2-556">Guid</span><span class="sxs-lookup"><span data-stu-id="053d2-556">Guid</span></span>|  
|<span data-ttu-id="053d2-557">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="053d2-557">DESCRIPTION</span></span>|<span data-ttu-id="053d2-558">String</span><span class="sxs-lookup"><span data-stu-id="053d2-558">String</span></span>|  
|<span data-ttu-id="053d2-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="053d2-559">TABLE_PROPID</span></span>|<span data-ttu-id="053d2-560">Int64</span><span class="sxs-lookup"><span data-stu-id="053d2-560">Int64</span></span>|  
|<span data-ttu-id="053d2-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="053d2-561">DATE_CREATED</span></span>|<span data-ttu-id="053d2-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="053d2-562">DateTime</span></span>|  
|<span data-ttu-id="053d2-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="053d2-563">DATE_MODIFIED</span></span>|<span data-ttu-id="053d2-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="053d2-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="053d2-565">Columnas</span><span class="sxs-lookup"><span data-stu-id="053d2-565">Columns</span></span>  
  
|<span data-ttu-id="053d2-566">ColumName</span><span class="sxs-lookup"><span data-stu-id="053d2-566">ColumnName</span></span>|<span data-ttu-id="053d2-567">DataType</span><span class="sxs-lookup"><span data-stu-id="053d2-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="053d2-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="053d2-568">TABLE_CATALOG</span></span>|<span data-ttu-id="053d2-569">String</span><span class="sxs-lookup"><span data-stu-id="053d2-569">String</span></span>|  
|<span data-ttu-id="053d2-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="053d2-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="053d2-571">String</span><span class="sxs-lookup"><span data-stu-id="053d2-571">String</span></span>|  
|<span data-ttu-id="053d2-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="053d2-572">TABLE_NAME</span></span>|<span data-ttu-id="053d2-573">String</span><span class="sxs-lookup"><span data-stu-id="053d2-573">String</span></span>|  
|<span data-ttu-id="053d2-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="053d2-574">COLUMN_NAME</span></span>|<span data-ttu-id="053d2-575">String</span><span class="sxs-lookup"><span data-stu-id="053d2-575">String</span></span>|  
|<span data-ttu-id="053d2-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="053d2-576">COLUMN_GUID</span></span>|<span data-ttu-id="053d2-577">Guid</span><span class="sxs-lookup"><span data-stu-id="053d2-577">Guid</span></span>|  
|<span data-ttu-id="053d2-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="053d2-578">COLUMN_PROPID</span></span>|<span data-ttu-id="053d2-579">Int64</span><span class="sxs-lookup"><span data-stu-id="053d2-579">Int64</span></span>|  
|<span data-ttu-id="053d2-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="053d2-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="053d2-581">Int64</span><span class="sxs-lookup"><span data-stu-id="053d2-581">Int64</span></span>|  
|<span data-ttu-id="053d2-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="053d2-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="053d2-583">Boolean</span><span class="sxs-lookup"><span data-stu-id="053d2-583">Boolean</span></span>|  
|<span data-ttu-id="053d2-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="053d2-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="053d2-585">String</span><span class="sxs-lookup"><span data-stu-id="053d2-585">String</span></span>|  
|<span data-ttu-id="053d2-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="053d2-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="053d2-587">Int64</span><span class="sxs-lookup"><span data-stu-id="053d2-587">Int64</span></span>|  
|<span data-ttu-id="053d2-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="053d2-588">IS_NULLABLE</span></span>|<span data-ttu-id="053d2-589">Boolean</span><span class="sxs-lookup"><span data-stu-id="053d2-589">Boolean</span></span>|  
|<span data-ttu-id="053d2-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="053d2-590">DATA_TYPE</span></span>|<span data-ttu-id="053d2-591">Int32</span><span class="sxs-lookup"><span data-stu-id="053d2-591">Int32</span></span>|  
|<span data-ttu-id="053d2-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="053d2-592">TYPE_GUID</span></span>|<span data-ttu-id="053d2-593">Guid</span><span class="sxs-lookup"><span data-stu-id="053d2-593">Guid</span></span>|  
|<span data-ttu-id="053d2-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="053d2-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="053d2-595">Int64</span><span class="sxs-lookup"><span data-stu-id="053d2-595">Int64</span></span>|  
|<span data-ttu-id="053d2-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="053d2-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="053d2-597">Int64</span><span class="sxs-lookup"><span data-stu-id="053d2-597">Int64</span></span>|  
|<span data-ttu-id="053d2-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="053d2-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="053d2-599">Int32</span><span class="sxs-lookup"><span data-stu-id="053d2-599">Int32</span></span>|  
|<span data-ttu-id="053d2-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="053d2-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="053d2-601">Int16</span><span class="sxs-lookup"><span data-stu-id="053d2-601">Int16</span></span>|  
|<span data-ttu-id="053d2-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="053d2-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="053d2-603">Int64</span><span class="sxs-lookup"><span data-stu-id="053d2-603">Int64</span></span>|  
|<span data-ttu-id="053d2-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="053d2-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="053d2-605">String</span><span class="sxs-lookup"><span data-stu-id="053d2-605">String</span></span>|  
|<span data-ttu-id="053d2-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="053d2-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="053d2-607">String</span><span class="sxs-lookup"><span data-stu-id="053d2-607">String</span></span>|  
|<span data-ttu-id="053d2-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="053d2-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="053d2-609">String</span><span class="sxs-lookup"><span data-stu-id="053d2-609">String</span></span>|  
|<span data-ttu-id="053d2-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="053d2-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="053d2-611">String</span><span class="sxs-lookup"><span data-stu-id="053d2-611">String</span></span>|  
|<span data-ttu-id="053d2-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="053d2-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="053d2-613">String</span><span class="sxs-lookup"><span data-stu-id="053d2-613">String</span></span>|  
|<span data-ttu-id="053d2-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="053d2-614">COLLATION_NAME</span></span>|<span data-ttu-id="053d2-615">String</span><span class="sxs-lookup"><span data-stu-id="053d2-615">String</span></span>|  
|<span data-ttu-id="053d2-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="053d2-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="053d2-617">String</span><span class="sxs-lookup"><span data-stu-id="053d2-617">String</span></span>|  
|<span data-ttu-id="053d2-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="053d2-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="053d2-619">String</span><span class="sxs-lookup"><span data-stu-id="053d2-619">String</span></span>|  
|<span data-ttu-id="053d2-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="053d2-620">DOMAIN_NAME</span></span>|<span data-ttu-id="053d2-621">String</span><span class="sxs-lookup"><span data-stu-id="053d2-621">String</span></span>|  
|<span data-ttu-id="053d2-622">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="053d2-622">DESCRIPTION</span></span>|<span data-ttu-id="053d2-623">String</span><span class="sxs-lookup"><span data-stu-id="053d2-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="053d2-624">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="053d2-624">Procedures</span></span>  
  
|<span data-ttu-id="053d2-625">ColumName</span><span class="sxs-lookup"><span data-stu-id="053d2-625">ColumnName</span></span>|<span data-ttu-id="053d2-626">DataType</span><span class="sxs-lookup"><span data-stu-id="053d2-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="053d2-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="053d2-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="053d2-628">String</span><span class="sxs-lookup"><span data-stu-id="053d2-628">String</span></span>|  
|<span data-ttu-id="053d2-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="053d2-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="053d2-630">String</span><span class="sxs-lookup"><span data-stu-id="053d2-630">String</span></span>|  
|<span data-ttu-id="053d2-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="053d2-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="053d2-632">String</span><span class="sxs-lookup"><span data-stu-id="053d2-632">String</span></span>|  
|<span data-ttu-id="053d2-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="053d2-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="053d2-634">Int16</span><span class="sxs-lookup"><span data-stu-id="053d2-634">Int16</span></span>|  
|<span data-ttu-id="053d2-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="053d2-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="053d2-636">String</span><span class="sxs-lookup"><span data-stu-id="053d2-636">String</span></span>|  
|<span data-ttu-id="053d2-637">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="053d2-637">DESCRIPTION</span></span>|<span data-ttu-id="053d2-638">String</span><span class="sxs-lookup"><span data-stu-id="053d2-638">String</span></span>|  
|<span data-ttu-id="053d2-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="053d2-639">DATE_CREATED</span></span>|<span data-ttu-id="053d2-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="053d2-640">DateTime</span></span>|  
|<span data-ttu-id="053d2-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="053d2-641">DATE_MODIFIED</span></span>|<span data-ttu-id="053d2-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="053d2-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="053d2-643">Vistas</span><span class="sxs-lookup"><span data-stu-id="053d2-643">Views</span></span>  
  
|<span data-ttu-id="053d2-644">ColumName</span><span class="sxs-lookup"><span data-stu-id="053d2-644">ColumnName</span></span>|<span data-ttu-id="053d2-645">DataType</span><span class="sxs-lookup"><span data-stu-id="053d2-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="053d2-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="053d2-646">TABLE_CATALOG</span></span>|<span data-ttu-id="053d2-647">String</span><span class="sxs-lookup"><span data-stu-id="053d2-647">String</span></span>|  
|<span data-ttu-id="053d2-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="053d2-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="053d2-649">String</span><span class="sxs-lookup"><span data-stu-id="053d2-649">String</span></span>|  
|<span data-ttu-id="053d2-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="053d2-650">TABLE_NAME</span></span>|<span data-ttu-id="053d2-651">String</span><span class="sxs-lookup"><span data-stu-id="053d2-651">String</span></span>|  
|<span data-ttu-id="053d2-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="053d2-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="053d2-653">String</span><span class="sxs-lookup"><span data-stu-id="053d2-653">String</span></span>|  
|<span data-ttu-id="053d2-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="053d2-654">CHECK_OPTION</span></span>|<span data-ttu-id="053d2-655">Boolean</span><span class="sxs-lookup"><span data-stu-id="053d2-655">Boolean</span></span>|  
|<span data-ttu-id="053d2-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="053d2-656">IS_UPDATABLE</span></span>|<span data-ttu-id="053d2-657">Boolean</span><span class="sxs-lookup"><span data-stu-id="053d2-657">Boolean</span></span>|  
|<span data-ttu-id="053d2-658">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="053d2-658">DESCRIPTION</span></span>|<span data-ttu-id="053d2-659">String</span><span class="sxs-lookup"><span data-stu-id="053d2-659">String</span></span>|  
|<span data-ttu-id="053d2-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="053d2-660">DATE_CREATED</span></span>|<span data-ttu-id="053d2-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="053d2-661">DateTime</span></span>|  
|<span data-ttu-id="053d2-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="053d2-662">DATE_MODIFIED</span></span>|<span data-ttu-id="053d2-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="053d2-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="053d2-664">Índices</span><span class="sxs-lookup"><span data-stu-id="053d2-664">Indexes</span></span>  
  
|<span data-ttu-id="053d2-665">ColumName</span><span class="sxs-lookup"><span data-stu-id="053d2-665">ColumnName</span></span>|<span data-ttu-id="053d2-666">DataType</span><span class="sxs-lookup"><span data-stu-id="053d2-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="053d2-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="053d2-667">TABLE_CATALOG</span></span>|<span data-ttu-id="053d2-668">String</span><span class="sxs-lookup"><span data-stu-id="053d2-668">String</span></span>|  
|<span data-ttu-id="053d2-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="053d2-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="053d2-670">String</span><span class="sxs-lookup"><span data-stu-id="053d2-670">String</span></span>|  
|<span data-ttu-id="053d2-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="053d2-671">TABLE_NAME</span></span>|<span data-ttu-id="053d2-672">String</span><span class="sxs-lookup"><span data-stu-id="053d2-672">String</span></span>|  
|<span data-ttu-id="053d2-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="053d2-673">INDEX_CATALOG</span></span>|<span data-ttu-id="053d2-674">String</span><span class="sxs-lookup"><span data-stu-id="053d2-674">String</span></span>|  
|<span data-ttu-id="053d2-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="053d2-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="053d2-676">String</span><span class="sxs-lookup"><span data-stu-id="053d2-676">String</span></span>|  
|<span data-ttu-id="053d2-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="053d2-677">INDEX_NAME</span></span>|<span data-ttu-id="053d2-678">String</span><span class="sxs-lookup"><span data-stu-id="053d2-678">String</span></span>|  
|<span data-ttu-id="053d2-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="053d2-679">PRIMARY_KEY</span></span>|<span data-ttu-id="053d2-680">Boolean</span><span class="sxs-lookup"><span data-stu-id="053d2-680">Boolean</span></span>|  
|<span data-ttu-id="053d2-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="053d2-681">UNIQUE</span></span>|<span data-ttu-id="053d2-682">Boolean</span><span class="sxs-lookup"><span data-stu-id="053d2-682">Boolean</span></span>|  
|<span data-ttu-id="053d2-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="053d2-683">CLUSTERED</span></span>|<span data-ttu-id="053d2-684">Boolean</span><span class="sxs-lookup"><span data-stu-id="053d2-684">Boolean</span></span>|  
|<span data-ttu-id="053d2-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="053d2-685">TYPE</span></span>|<span data-ttu-id="053d2-686">Int32</span><span class="sxs-lookup"><span data-stu-id="053d2-686">Int32</span></span>|  
|<span data-ttu-id="053d2-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="053d2-687">FILL_FACTOR</span></span>|<span data-ttu-id="053d2-688">Int32</span><span class="sxs-lookup"><span data-stu-id="053d2-688">Int32</span></span>|  
|<span data-ttu-id="053d2-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="053d2-689">INITIAL_SIZE</span></span>|<span data-ttu-id="053d2-690">Int32</span><span class="sxs-lookup"><span data-stu-id="053d2-690">Int32</span></span>|  
|<span data-ttu-id="053d2-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="053d2-691">NULLS</span></span>|<span data-ttu-id="053d2-692">Int32</span><span class="sxs-lookup"><span data-stu-id="053d2-692">Int32</span></span>|  
|<span data-ttu-id="053d2-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="053d2-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="053d2-694">Boolean</span><span class="sxs-lookup"><span data-stu-id="053d2-694">Boolean</span></span>|  
|<span data-ttu-id="053d2-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="053d2-695">AUTO_UPDATE</span></span>|<span data-ttu-id="053d2-696">Boolean</span><span class="sxs-lookup"><span data-stu-id="053d2-696">Boolean</span></span>|  
|<span data-ttu-id="053d2-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="053d2-697">NULL_COLLATION</span></span>|<span data-ttu-id="053d2-698">Int32</span><span class="sxs-lookup"><span data-stu-id="053d2-698">Int32</span></span>|  
|<span data-ttu-id="053d2-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="053d2-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="053d2-700">Int64</span><span class="sxs-lookup"><span data-stu-id="053d2-700">Int64</span></span>|  
|<span data-ttu-id="053d2-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="053d2-701">COLUMN_NAME</span></span>|<span data-ttu-id="053d2-702">String</span><span class="sxs-lookup"><span data-stu-id="053d2-702">String</span></span>|  
|<span data-ttu-id="053d2-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="053d2-703">COLUMN_GUID</span></span>|<span data-ttu-id="053d2-704">Guid</span><span class="sxs-lookup"><span data-stu-id="053d2-704">Guid</span></span>|  
|<span data-ttu-id="053d2-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="053d2-705">COLUMN_PROPID</span></span>|<span data-ttu-id="053d2-706">Int64</span><span class="sxs-lookup"><span data-stu-id="053d2-706">Int64</span></span>|  
|<span data-ttu-id="053d2-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="053d2-707">COLLATION</span></span>|<span data-ttu-id="053d2-708">Int16</span><span class="sxs-lookup"><span data-stu-id="053d2-708">Int16</span></span>|  
|<span data-ttu-id="053d2-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="053d2-709">CARDINALITY</span></span>|<span data-ttu-id="053d2-710">Decimal</span><span class="sxs-lookup"><span data-stu-id="053d2-710">Decimal</span></span>|  
|<span data-ttu-id="053d2-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="053d2-711">PAGES</span></span>|<span data-ttu-id="053d2-712">Int32</span><span class="sxs-lookup"><span data-stu-id="053d2-712">Int32</span></span>|  
|<span data-ttu-id="053d2-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="053d2-713">FILTER_CONDITION</span></span>|<span data-ttu-id="053d2-714">String</span><span class="sxs-lookup"><span data-stu-id="053d2-714">String</span></span>|  
|<span data-ttu-id="053d2-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="053d2-715">INTEGRATED</span></span>|<span data-ttu-id="053d2-716">Booleano</span><span class="sxs-lookup"><span data-stu-id="053d2-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="053d2-717">Vea también</span><span class="sxs-lookup"><span data-stu-id="053d2-717">See also</span></span>
- [<span data-ttu-id="053d2-718">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="053d2-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
