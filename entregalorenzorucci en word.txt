-- MySQL dump 10.13  Distrib 8.0.27, for Win64 (x86_64)
--
-- Host: localhost    Database: entregalorenzorucci
-- ------------------------------------------------------
-- Server version	8.0.27

/*!40101 SET @OLD_CHARACTER_SET_CLIENT=@@CHARACTER_SET_CLIENT */;
/*!40101 SET @OLD_CHARACTER_SET_RESULTS=@@CHARACTER_SET_RESULTS */;
/*!40101 SET @OLD_COLLATION_CONNECTION=@@COLLATION_CONNECTION */;
/*!50503 SET NAMES utf8 */;
/*!40103 SET @OLD_TIME_ZONE=@@TIME_ZONE */;
/*!40103 SET TIME_ZONE='+00:00' */;
/*!40014 SET @OLD_UNIQUE_CHECKS=@@UNIQUE_CHECKS, UNIQUE_CHECKS=0 */;
/*!40014 SET @OLD_FOREIGN_KEY_CHECKS=@@FOREIGN_KEY_CHECKS, FOREIGN_KEY_CHECKS=0 */;
/*!40101 SET @OLD_SQL_MODE=@@SQL_MODE, SQL_MODE='NO_AUTO_VALUE_ON_ZERO' */;
/*!40111 SET @OLD_SQL_NOTES=@@SQL_NOTES, SQL_NOTES=0 */;

--
-- Table structure for table `categorias`
--

DROP TABLE IF EXISTS `categorias`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `categorias` (
  `id_Categorias` int NOT NULL AUTO_INCREMENT,
  `Categorias` varchar(45) DEFAULT NULL,
  PRIMARY KEY (`id_Categorias`),
  UNIQUE KEY `id_Categorias_UNIQUE` (`id_Categorias`),
  CONSTRAINT `Fk_id_categorias` FOREIGN KEY (`id_Categorias`) REFERENCES `notas` (`id_Notas`)
) ENGINE=InnoDB AUTO_INCREMENT=11 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `categorias`
--

LOCK TABLES `categorias` WRITE;
/*!40000 ALTER TABLE `categorias` DISABLE KEYS */;
INSERT INTO `categorias` VALUES (1,'peliculas'),(2,'documentales'),(3,'musica'),(4,'deporte'),(5,'filosofia'),(6,'automotor'),(7,'economia'),(8,'policiales'),(9,'politica'),(10,'celebridades');
/*!40000 ALTER TABLE `categorias` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `notas`
--

DROP TABLE IF EXISTS `notas`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `notas` (
  `id_Notas` int NOT NULL AUTO_INCREMENT,
  `titulo` varchar(100) NOT NULL,
  `date_created` date DEFAULT NULL,
  `date_modif` date DEFAULT NULL,
  `descripcion` varchar(2000) DEFAULT NULL,
  `Fk_id_categoria` int NOT NULL,
  `Fk_id_usuario` int NOT NULL,
  PRIMARY KEY (`id_Notas`),
  UNIQUE KEY `id_Notas_UNIQUE` (`id_Notas`),
  KEY `Fk_id_categoria_idx` (`Fk_id_categoria`),
  KEY `Fk_id_usuario_idx` (`Fk_id_usuario`),
  CONSTRAINT `Fk_id_categoria` FOREIGN KEY (`Fk_id_categoria`) REFERENCES `categorias` (`id_Categorias`),
  CONSTRAINT `Fk_id_usuario` FOREIGN KEY (`Fk_id_usuario`) REFERENCES `usuarios` (`Id`)
) ENGINE=InnoDB AUTO_INCREMENT=11 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `notas`
--

LOCK TABLES `notas` WRITE;
/*!40000 ALTER TABLE `notas` DISABLE KEYS */;
INSERT INTO `notas` VALUES (1,'t',NULL,NULL,NULL,1,1),(2,'i',NULL,NULL,NULL,2,2),(3,'t',NULL,NULL,NULL,3,3),(4,'u',NULL,NULL,NULL,4,4),(5,'l',NULL,NULL,NULL,5,5),(6,'o',NULL,NULL,NULL,6,6),(7,'t',NULL,NULL,NULL,7,7),(8,'i',NULL,NULL,NULL,8,8),(9,'t',NULL,NULL,NULL,9,9),(10,'u',NULL,NULL,NULL,10,10);
/*!40000 ALTER TABLE `notas` ENABLE KEYS */;
UNLOCK TABLES;

--
-- Table structure for table `usuarios`
--

DROP TABLE IF EXISTS `usuarios`;
/*!40101 SET @saved_cs_client     = @@character_set_client */;
/*!50503 SET character_set_client = utf8mb4 */;
CREATE TABLE `usuarios` (
  `Id` int NOT NULL AUTO_INCREMENT,
  `Id_usuario` varchar(25) NOT NULL,
  `Id_email` varchar(45) NOT NULL,
  PRIMARY KEY (`Id`),
  UNIQUE KEY `idId_UNIQUE` (`Id`)
) ENGINE=InnoDB AUTO_INCREMENT=11 DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_0900_ai_ci;
/*!40101 SET character_set_client = @saved_cs_client */;

--
-- Dumping data for table `usuarios`
--

LOCK TABLES `usuarios` WRITE;
/*!40000 ALTER TABLE `usuarios` DISABLE KEYS */;
INSERT INTO `usuarios` VALUES (1,'Lorenzo','lorenzo@mail'),(2,'Miguel','Miguel@mail'),(3,'Maria','Maria@mail'),(4,'Susana','Susana@mail'),(5,'Guillermo','Guillermo@mail'),(6,'Julieta','Julieta@mail'),(7,'Vanessa','Vanessa@mail'),(8,'Belen','Belen@mail'),(9,'Marcos','Marcos@mail'),(10,'Lucas','Lucas@mail');
/*!40000 ALTER TABLE `usuarios` ENABLE KEYS */;
UNLOCK TABLES;
/*!40103 SET TIME_ZONE=@OLD_TIME_ZONE */;

/*!40101 SET SQL_MODE=@OLD_SQL_MODE */;
/*!40014 SET FOREIGN_KEY_CHECKS=@OLD_FOREIGN_KEY_CHECKS */;
/*!40014 SET UNIQUE_CHECKS=@OLD_UNIQUE_CHECKS */;
/*!40101 SET CHARACTER_SET_CLIENT=@OLD_CHARACTER_SET_CLIENT */;
/*!40101 SET CHARACTER_SET_RESULTS=@OLD_CHARACTER_SET_RESULTS */;
/*!40101 SET COLLATION_CONNECTION=@OLD_COLLATION_CONNECTION */;
/*!40111 SET SQL_NOTES=@OLD_SQL_NOTES */;

-- Dump completed on 2022-01-29  2:13:46
