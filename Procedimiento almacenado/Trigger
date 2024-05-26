Procedimiento almacenado 
DELIMITER //
CREATE PROCEDURE  city_con_letra(in letra CHAR, out numero int)
	BEGIN
	SELECT count(*) into numero
	FROM city
	WHERE Name like concat(letra,’%’);
	END//
	DELIMITER ;

CALL city_con_letra(‘B’,  @nameB);
CALL city_con_letra(‘G’,  @nameG);
CALL city_con_letra(‘M’,  @nameM);

SELECT @nameB as ciudades_con_B, @nameG as ciudades_con_G, @nameM as ciudades_con_M;

Trigger
DELIMITER //
CREATE TRIGGER log_world AFTER INSERT ON city  
FOR EACH ROW 
BEGIN
    INSERT INTO acciones(accion) VALUES 
    (CONCAT('Se creó un registro en nombre: ', NEW.Name,', ID: ', NEW.id));
END//

DELIMITER ;
