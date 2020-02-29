Help on module meeus:

NAME
    meeus

DESCRIPTION
    Impl�mentation des "calculs astronomiques � l'usage des amateurs"
    de Jean MEEUS, �dition 2014.

FUNCTIONS
    avantjj0(Y, M, D)
        V�rifie si une date (Y, M, D) se trouve avant le jour julien 0, c'est
        � dire avant le 1er janvier - 4712 � 12H (-4712, 1, 1.5).
        Entr�e :
            Y L'ann�e
            M le num�ro du mois
            D le jour du mois avec �ventuellement des d�cimales de jour
        Retour :
            booleen : True or False
            erreur : si (Y, M, D) n'est pas une date conforme
                - voir conforme(Y, M, D) -
    
    bissextile(Y)
        V�rifie si une ann�e Y est bissextile.
        Entr�e :
            Y l�ann�e
        Retour :
            True
            False
            Erreur si Y n�est pas convertible en entier
    
    calendrier(Y, M, D)
        Retourne le calendrier (Julien ou Gregorien) qui correspond � une date.
        Entr�e :
            Y l�ann�e
            M le num�ro du mois
            D le jour du mois avec �ventuellement des d�cimales de jour
        Retour :
            � Julien �
            � Gr�gorien �
            Erreur si (Y, M, D) n�est pas une date conforme
                - voir conforme(Y, M, D) -
    
    conforme(Y, M, D)
        V�rifie la conformit� de la date propos�e.
        Entr�e :
            Y l�ann�e
            M le num�ro du mois
            D le jour du mois avec �ventuellement des d�cimales de jour
        Retour :
            [Y, M, D]
            Y l�ann�e
            M le num�ro du mois
            D le jour du mois avec �ventuellement des d�cimales de jour
            Erreur si :
                le mois n�est pas compris entre 1 et 12
                le nombre de jours n�est pas correct pour le mois et l�ann�e.
                si la date correspond � un jour perdu lors que changement de
                calendrier Julien vers Gr�gorien
    
    coordonnees_moyennes(HR, A)
        Calcul approximatif des coordonn�es moyennes de l'�toile:
            en ascenscion droite
            et en d�clinaison de
        pour l'ann�e A.
        Entr�e :
            HR = num�ro de l'�toile
            A = Ann�e
        Sortie :
            dictionnaire :
            'calculs' = calculs interm�diaires pour d�bogage
            'RAf (�)' = ascension droite (�) de 0 � 360�
            'DEf (�)' = d�clinaison (�) de -90 � +90�
    
    coordonnees_moyennes2(HR, A)
        Calcul les coordonn�es moyennes de l'�toile:
            en ascenscion droite
            et en d�clinaison de
        pour l'ann�e A premi�re m�thode matricielle.
        Entr�e :
            HR = num�ro de l'�toile
            A = Ann�e
        Sortie :
            dictionnaire :
            'calculs' = calculs interm�diaires pour d�bogage
            'RAf (�)' = ascension droite (�) de 0 � 360�
            'DEf (�)' = d�clinaison (�) de -90 � +90�
    
    coordonnees_moyennes3(HR, A)
        Calcul les coordonn�es moyennes de l'�toile:
            en ascenscion droite
            et en d�clinaison de
        pour l'ann�e A deuxi�me m�thode matricielle.
        Entr�e :
            HR = num�ro de l'�toile
            A = Ann�e
        Sortie :
            dictionnaire :
            'calculs' = calculs interm�diaires pour d�bogage
            'RAf (�)' = ascension droite (�) de 0 � 360�
            'DEf (�)' = d�clinaison (�) de -90 � +90�
    
    coordonnees_moyennes_rigoureuses(HR, A)
        Calcul rigoureux des coordonn�es moyennes de l'�toile:
            en ascenscion droite
            et en d�clinaison de
        pour l'ann�e A.
        Entr�e :
            HR = num�ro de l'�toile
            A = Ann�e
        Sortie :
            dictionnaire :
            'calculs' = calculs interm�diaires pour d�bogage
            'RAf (�)' = ascension droite (�) de 0 � 360�
            'DEf (�)' = d�clinaison (�) de -90 � +90�
    
    date(JJ)
        D�termine la date du calendrier � partir du jour julien.
        La m�thode suivante est valable pour les ann�es positives aussi bien
        que n�gatives, mais non pour les jours juliens n�gatifs.
        Entr�e :
            JJ le jour julien
        Retour :
            [Y, M, D]
            Y l�ann�e
            M le num�ro du mois
            D le jour du mois avec �ventuellement des d�cimales de jour
            Erreur si :
                JJ n�est pas convertible en float
                JJ < 0
    
    dimanchepaques(Y)
        Calcul la date du jour de P�ques de l'ann�e Y.
        Entr�e :
            Y l�ann�e
        Retour :
            [Y, M, D]
            Y l�ann�e
            M le num�ro du mois
            D le jour du mois
            Erreur si Y n�est pas convertible en entier
    
    jourannee(Y, M, D)
        D�termine le num�ro de jour de l'ann�e correspondant � une date.
        Entr�e :
            Y l�ann�e
            M le num�ro du mois
            D le jour du mois avec �ventuellement des d�cimales de jour
        Retour :
            N num�ro du jour de l�ann�e
            Entre 1 et 365 pour une ann�e r�guli�re
            Entre 1 et 366 pour une ann�e bissextile
            Erreur si (Y, M, D) n�est pas une date conforme
                - voir conforme(Y, M, D) -
    
    jourjulien(Y, M, D)
        D�termine la valeur du jour julien qui correspond � une date donn�e.
        Cette m�thode est valable aussi bien pour les ann�es positives que
        n�gatives, mais pas pour des jours juliens n�gatifs.
        Entr�e :
            Y l�ann�e
            M le num�ro du mois
            D le jour du mois avec �ventuellement des d�cimales de jour
        Retour :
            JJ jour julien
            Erreur si :
                avantjj0(Y, M, D)
                (Y, M, D) n�est pas une date conforme
                    - voir conforme(Y, M, D) �
    
    jourjulien0(Y)
        D�termine le jour julien correspondant au 0.0 janvier de l'ann�e Y.
        Cette m�thode est valable aussi bien pour les ann�es positives que
        n�gatives, mais pas pour des jours juliens n�gatifs.
        Entr�e :
            Y l�ann�e
        Retour :
            JJ jour julien
            Erreur si :
                Y n�est pas convertible en entier
                Y < -4711
    
    jourjulienmodif(Y, M, D)
        D�termine la valeur du jour julien modifi� (MDJ) qui correspond
        � une date donn�e.
        MDJ = JJ - 2 400 000,5
        L'origine de cette �chelle est le 17 novembre 1858 � 0h.
        Cette m�thode est valable aussi bien pour les ann�es positives que
        n�gatives, mais pas pour des jours juliens n�gatifs.
        Entr�e :
            Y l�ann�e
            M le num�ro du mois
            D le jour du mois avec �ventuellement des d�cimales de jour
        Retour :
            JJ jour julien
            Erreur si :
                avantjj0(Y, M, D)
                (Y, M, D) n�est pas une date conforme
                    - voir conforme(Y, M, D) �
    
    joursemaine(Y, M, D)
        D�termine le jour de la semaine correspondant � une date.
        Entr�e :
            Y l�ann�e
            M le num�ro du mois
            D le jour du mois avec �ventuellement des d�cimales de jour
        Retour :
            Jour de la semaine (lundi, mardi, �.)
            Erreur si (Y, M, D) n�est pas une date conforme
                - voir conforme(Y, M, D) �
    
    parametres_precession(t)
        Calcul les param�tres de la pr�cession approximative.
        Entr�e :
            t en si�cles juliens � partir de l'�poque 2000.0
                t = [(JJ) - (JJ)2000.0] / 36525
        Retour :
            dictionnaire:
            m_alpha (s)
            n_alpha (s)
            n_delta (")

DATA
    jours_semaine = {0: 'dimanche', 1: 'lundi', 2: 'mardi', 3: 'mercredi',...

FILE
    c:\users\mc\mu_code\_mes_modules\meeuscalc\meeus.py


