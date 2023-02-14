BEGIN;

### Categoria 1: 5 preguntes de consultes simples: inclou una sola taula, funcions, funcions d'agregat o grups. (0,5 punts)

#### <em>Mostra els candidats que tenen mes de xxx anys</em>

SELECT TIMESTAMPDIFF(YEAR,data_naixement,CURDATE()) AS Edat<br>
	FROM persones<br>
WHERE TIMESTAMPDIFF(YEAR,data_naixement,CURDATE()) >= 25;


#### <em>Mostra els municipis que tenen en el nom xxx</em>

SELECT *<br>
	FROM municipis;

#### <em>Mostra el nom complet dels candidats</em>

SELECT CONCAT(nom, ' ',cog1 , ' ' ,cog2) AS Nom_complet<br>
	FROM persones;

#### <em>Recompte de vots al mes X</em>

SELECT COUNT(eleccions_id) as vots<br>
	FROM eleccions<br>
WHERE MONTH (mes) = ?;

### Categoria 2: 5 preguntes de consultes de combinacions de més d'una taula: INNER JOINS, LEFT JOINS. (1 punt)

#### <em>Mostra als candidats que han estat mes de xx vegades com a S = suplent</em>








-- CATEGORIA 3
-- Categoria 3: 5 preguntes fent ús de subconsultes (1 punt)







-- CATEGORIA 4
-- Categoria 4: 1 pregunta utilitzant WINDOW FUNCTIONS o recursivitat (1 punt)
WITH RECURSIVE codi (n) AS (
SELECT 1
UNION
SELECT n + 1
FROM codi
WHERE n < 10
)
SELECT n, m.*
	FROM codi a
    INNER JOIN municipis1 m ON m.codi_ine = a.n;


COMMIT;