# dev-m2.task.05
Consultas sobre tblLocalidades



SELECT EntidadId,   MAX(PoblacionTotal) as poblacion
  FROM [dbo].[Localidad]
  GROUP BY EntidadId order by poblacion desc

select * from dbo.Localidad 
where EntidadId = 9
and PoblacionTotal = 1835486
 



/*
1) Top 10 de localidades más pobladas
2) Top 10 de localidades con más mujeres
3) Top 10 de localidades con más hombres
4) Top 10 de localidades con menos hombres y que sea mayor a 0
5) Top 10 de localidades con menos mujeres y que sea mayor a 0
*/



SELECT TOP (10) tEntidad.EntidadId, tEntidad.Nombre as NombreEntidad, 
tLoc.MunicipioId, x.Nombre as NombreMunicipio,
tLoc.LocalidadId, tLoc.Nombre 
FROM Localidad as tLoc
INNER JOIN EntidadFederativa AS tEntidad ON tEntidad.EntidadId = tLoc.EntidadId
INNER JOIN Municipio AS x ON x.MunicipioId = tLoc.MunicipioId

/*
Sobre tblMucipio

Obtener el Nombre del la Entidad a la que pertenece, Nombre del Municipio, Poblacion Femenina, Poblacion Másculina
Obtener las entididades federativas segun la division ecónomica de México
Obtener coordenada maxima y minima de  Ciudad de México 
Obtener coordenada maxima y minima de  Bajacalifornia Sur
Obtener coordenada maxima y minima de  Meridad 

*/


SELECT count(nombre)  FROM Municipio where Nombre like '%J%'

/*
Obtener los municipios que en su nombre contengan el nombre de Pedro
Obtener los municipios que en su nombre contengan el nombre maria
Obtener los municipios que en su nombre contengan el nombre maria y su poblacion total sea mayor a 1000

*/
