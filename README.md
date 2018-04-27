# yummy_back

PHP-Slim-Yummy
```
-- phpMyAdmin SQL Dump
-- version 4.6.4
-- https://www.phpmyadmin.net/
--
-- Client :  127.0.0.1
-- Généré le :  Ven 27 Avril 2018 à 02:42
-- Version du serveur :  5.7.14
-- Version de PHP :  5.6.25

SET SQL_MODE = "NO_AUTO_VALUE_ON_ZERO";
SET time_zone = "+00:00";


/*!40101 SET @OLD_CHARACTER_SET_CLIENT=@@CHARACTER_SET_CLIENT */;
/*!40101 SET @OLD_CHARACTER_SET_RESULTS=@@CHARACTER_SET_RESULTS */;
/*!40101 SET @OLD_COLLATION_CONNECTION=@@COLLATION_CONNECTION */;
/*!40101 SET NAMES utf8mb4 */;

--
-- Base de données :  `banan`
--
CREATE DATABASE IF NOT EXISTS `banan` DEFAULT CHARACTER SET latin1 COLLATE latin1_swedish_ci;
USE `banan`;

-- --------------------------------------------------------

--
-- Structure de la table `cmd`
--

DROP TABLE IF EXISTS `cmd`;
CREATE TABLE `cmd` (
  `cmd_id` int(11) NOT NULL,
  `cmd` text,
  `price` decimal(10,0) NOT NULL,
  `user_id_fk` int(11) DEFAULT NULL,
  `created` int(11) DEFAULT NULL
) ENGINE=MyISAM DEFAULT CHARSET=latin1;

--
-- Contenu de la table `cmd`
--

INSERT INTO `cmd` (`cmd_id`, `cmd`, `price`, `user_id_fk`, `created`) VALUES
(1, 'Falafel', '4', 1, 1524440401),
(2, 'Thé noir', '2', 1, 1524440439),
(57, 'Thé noir', '2', 5, 1524790275),
(56, 'Donut choco noisette', '2', 5, 1524790269),
(55, 'Chocolat noir', '3', 5, 1524790253),
(50, 'Omelette', '5', 5, 1524790205),
(51, 'Falafel', '4', 5, 1524790213),
(52, 'Perrier', '2', 5, 1524790221),
(53, 'Orangina', '2', 5, 1524790231),
(54, 'Tarte aux noix', '3', 5, 1524790241),
(58, 'Café', '2', 5, 1524790294),
(59, '3 Fromages', '5', 8, 1524795986),
(60, 'Café', '2', 8, 1524796052),
(61, 'Donut choco noisette', '2', 8, 1524796074),
(62, 'Tarte aux noix', '3', 8, 1524796078),
(64, 'Cacahuètes', '3', 8, 1524796100);

-- --------------------------------------------------------

--
-- Structure de la table `emailusers`
--

DROP TABLE IF EXISTS `emailusers`;
CREATE TABLE `emailusers` (
  `user_id` int(11) NOT NULL,
  `email` varchar(300) DEFAULT NULL,
  `name` varchar(100) DEFAULT NULL
) ENGINE=MyISAM DEFAULT CHARSET=latin1;

-- --------------------------------------------------------

--
-- Structure de la table `imagesdata`
--

DROP TABLE IF EXISTS `imagesdata`;
CREATE TABLE `imagesdata` (
  `img_id` int(11) NOT NULL,
  `b64` text,
  `user_id_fk` int(11) DEFAULT NULL
) ENGINE=MyISAM DEFAULT CHARSET=latin1;

-- --------------------------------------------------------

--
-- Structure de la table `menu`
--

DROP TABLE IF EXISTS `menu`;
CREATE TABLE `menu` (
  `menu_id` int(11) NOT NULL,
  `name` varchar(255) DEFAULT NULL,
  `type` varchar(9) NOT NULL,
  `price` decimal(3,0) NOT NULL DEFAULT '5'
) ENGINE=MyISAM DEFAULT CHARSET=latin1;

--
-- Contenu de la table `menu`
--

INSERT INTO `menu` (`menu_id`, `name`, `type`, `price`) VALUES
(1, 'Falafel', 'Sandwish', '4'),
(2, '3 Fromages', 'Sandwish', '5'),
(3, 'Bacon', 'Sandwish', '6'),
(4, 'Jambon', 'Sandwish', '6'),
(5, 'Omelette', 'Sandwish', '5'),
(6, 'Perrier', 'Drink', '2'),
(7, 'Jus Fruit Rouge', 'Drink', '2'),
(8, 'Orangina', 'Drink', '2'),
(9, 'Coca', 'Drink', '2'),
(10, 'Coca Zéro', 'Drink', '2'),
(11, 'Compote de pomme', 'Dessert', '2'),
(12, 'Café', 'Drink', '2'),
(13, 'Cookie chocolat', 'Dessert', '2'),
(14, 'Donut choco noisette', 'Dessert', '2'),
(15, 'Perles coco', 'Dessert', '2'),
(16, 'Tarte aux noix', 'Dessert', '3'),
(17, 'Thé noir', 'Drink', '2'),
(18, 'Thé vert', 'Drink', '2'),
(19, 'Amandes', 'Snack', '4'),
(20, 'Cacahuètes', 'Snack', '3'),
(21, 'Chocolat noir', 'Snack', '3'),
(22, 'Curly', 'Snack', '3'),
(23, 'Noix de cajou', 'Snack', '4'),
(24, 'Heineken', 'Drink', '2');

-- --------------------------------------------------------

--
-- Structure de la table `users`
--

DROP TABLE IF EXISTS `users`;
CREATE TABLE `users` (
  `user_id` int(11) NOT NULL,
  `username` varchar(50) DEFAULT NULL,
  `password` varchar(300) DEFAULT NULL,
  `name` varchar(200) DEFAULT NULL,
  `email` varchar(300) DEFAULT NULL
) ENGINE=MyISAM DEFAULT CHARSET=latin1;

--
-- Contenu de la table `users`
--

INSERT INTO `users` (`user_id`, `username`, `password`, `name`, `email`) VALUES
(1, 'lewis', '24e02ac6f74199178187518e3ac412ff64718070611f6473e5e1c643b21ad984', 'lewis', 'l.w@g.com'),
(2, 'azhsb', '4bbe46f40c50fe67a7dc42df546ab57953e0ae77bfad4ae69c9af90b0640507e', 'lx', 'lx.f@h.fr'),
(3, 'ggggg', '1a11c579674473939687e9f79b12def6de071bead10cc3e3b11a554199d0d99b', 'jhkgjf', 'lkgf.ljh@kjh.lh'),
(4, 'test', '1a11c579674473939687e9f79b12def6de071bead10cc3e3b11a554199d0d99b', 'test', 'test.t@t.fr'),
(5, 'test2', '24e02ac6f74199178187518e3ac412ff64718070611f6473e5e1c643b21ad984', 'test2', 'test2.t@gmail.com'),
(6, 'test3', '1a11c579674473939687e9f79b12def6de071bead10cc3e3b11a554199d0d99b', 'test3', 'test3.t@gmail.com'),
(7, 'test4', '24e02ac6f74199178187518e3ac412ff64718070611f6473e5e1c643b21ad984', 'test4', 'test4.t@gmail.com'),
(8, 'Robert', '2238dd61a1bf83816b40ad894518814b8edf7221d84d897ffd2c0466ace07c41', 'Robert', 'rob.b@gmail.com');

--
-- Index pour les tables exportées
--

--
-- Index pour la table `cmd`
--
ALTER TABLE `cmd`
  ADD PRIMARY KEY (`cmd_id`);

--
-- Index pour la table `emailusers`
--
ALTER TABLE `emailusers`
  ADD PRIMARY KEY (`user_id`);

--
-- Index pour la table `imagesdata`
--
ALTER TABLE `imagesdata`
  ADD PRIMARY KEY (`img_id`);

--
-- Index pour la table `menu`
--
ALTER TABLE `menu`
  ADD PRIMARY KEY (`menu_id`);

--
-- Index pour la table `users`
--
ALTER TABLE `users`
  ADD PRIMARY KEY (`user_id`);

--
-- AUTO_INCREMENT pour les tables exportées
--

--
-- AUTO_INCREMENT pour la table `cmd`
--
ALTER TABLE `cmd`
  MODIFY `cmd_id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=65;
--
-- AUTO_INCREMENT pour la table `emailusers`
--
ALTER TABLE `emailusers`
  MODIFY `user_id` int(11) NOT NULL AUTO_INCREMENT;
--
-- AUTO_INCREMENT pour la table `imagesdata`
--
ALTER TABLE `imagesdata`
  MODIFY `img_id` int(11) NOT NULL AUTO_INCREMENT;
--
-- AUTO_INCREMENT pour la table `menu`
--
ALTER TABLE `menu`
  MODIFY `menu_id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=25;
--
-- AUTO_INCREMENT pour la table `users`
--
ALTER TABLE `users`
  MODIFY `user_id` int(11) NOT NULL AUTO_INCREMENT, AUTO_INCREMENT=9;
/*!40101 SET CHARACTER_SET_CLIENT=@OLD_CHARACTER_SET_CLIENT */;
/*!40101 SET CHARACTER_SET_RESULTS=@OLD_CHARACTER_SET_RESULTS */;
/*!40101 SET COLLATION_CONNECTION=@OLD_COLLATION_CONNECTION */;

```
