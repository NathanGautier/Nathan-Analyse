###on modifie la table isospeciality pour y ajouter le champ color
ALTER TABLE isospeciality
ADD color CHAR(7) DEFAULT '#FFFFFF';

###on met a jour les couleurs
UPDATE isospeciality
SET color='#00ccff'
WHERE tag='Anglais';

UPDATE isospeciality
SET color='#33ff33'
WHERE tag='Divers Cloud';

UPDATE isospeciality
SET color='#99ffcc'
WHERE tag='Cloud IA';

UPDATE isospeciality
SET color='#3366ff'
WHERE tag='Cloud Agile';

UPDATE isospeciality
SET color='#ffcc66'
WHERE tag='Android';