# honours-project
My honours project in Applied Statistics
Comparing Activity Profiles of
Different Playing Positions in Rugby
League Using Hidden Markov Models
Abstract
Hidden Markov models (HMMs) have been successfully applied to categorise animal movement
data into discrete activity states (e.g. moving, foraging for food, sleeping), but few studies have
sought to apply these models to player movement data in sports.
Rugby league is an invasion-type sport that involves complex player movement, where players
are assigned different playing positions that equate to performing different roles in matches.
There is a wealth of literature that has applied univariate approaches to highlighting differences
in activity profiles between playing positions in rugby league, but this approach cannot capture
the inherent complexity of player movement.
This project investigates the effect of player position on the activity profiles of professional
rugby league players, by fitting HMMs to player GPS and accelerometer data, and comparing
the resultant activity profiles across player positions. Most of the results corroborated the
existing rugby league activity profiling literature and thus demonstrated the effectiveness of
HMMs in modelling the movement of sports players. This project lays the foundation for
further application of HMMs to sports analytics.
1.1 Background and Context of Research
Statistical analysis of competitive sports has seen a remarkable surge in popularity over recent
years, which is mostly attributable to the ease with which data can now be collected (Groll and
Liebl, 2022). Player movement and activity can be measured in detail thanks to the advent of
GPS technology, allowing analysts to gain deeper insights into the performance of teams and
players (Aughey, 2011). With technology continuing to advance, the use of advanced analytics
is likely to become more crucial across all sports for teams and players to gain a competitive
advantage.
One important aspect of sports analytics is the activity profiling of athletes. This technique
is primarily concerned with the physical movements and activities of players during training
and matchplay. Activity profiling has been widely used across a range of sports, including
rugby league, to help improve physiological development and training (Gabbett et al., 2014;
Johnston et al., 2019). However, most of the existing research relies on a univariate approach
using descriptive statistics. While this approach is useful and popular amongst analysts, HMMs
could provide a novel alternative approach that uncovers deeper, more nuanced insights. HMMs
are able to capture multiple dimensions of movement simultaneously, allowing a greater degree
of complexity to be encapsulated.
HMMs have primarily been used to model the movement of animals, categorizing the movement
data into different behavioural states (Macdonald and Raubenheimer, 1995; Franke et al.,
2004; Patterson et al., 2009). Most of this research involves data taken over wide intervals
since ecologists are generally more interested in the broad-scale movement patterns of animals.
HMMs have not yet been applied to human movement data in rugby league matchplay. This
approach involves data recorded at a much higher frequency than animal tracking data, however,
the technique should work in a similar manner. Animal movement patterns are generally

measured at a broader scale (at least 1 minute between observations) since they are unlikely to
change back and forth between states rapidly (Kays et al., 2023). On the contrary, rugby league
involves dynamic player movement. Individuals may change back and forth between walking
and sprinting several times a minute, which necessitates a higher frequency of observations.
1.2 Overview of Rugby League
Rugby league is a contact sport that involves complex sequences of player movement. Each
team is comprised of 13 players, each assigned to a specific position with a corresponding
role and set of actions associated with it. Figure 1 shows a breakdown of the positions of a
rugby league team. The broadest categorization of positions is between the forwards (prop,
hooker, second-row, lock) and backs (halfback, five-eighth, centre, wing, fullback). These two
groups play substantially different roles in rugby league matches. Forwards are generally larger,
stronger, and more involved in tackling and collisions. Backs are generally faster, more agile,
and more involved in ball distribution and playmaking. While there is a significant difference
between forwards and backs, there is still significant variation between positions within these
two groups. Each position has a highly specialized role and, consequently, we are likely to
observe variation between the activity profiles of each position
A typical rugby league field is 68 metres wide and 112-122 metres long. H-shaped posts are
situated at both ends of the field. The general shape of a rugby league field is given in Figure 2.

Matches consist of two halves of 40 minutes each, during which each team attempts to obtain
possession of the oval-shaped ball and progress it over the opposition team’s try-line. The most
common method of scoring is the try, which is worth 4 points and involves grounding the ball
in the opposition’s in-goal area. Other methods of scoring include penalty goals (2 points),
conversions(2 points), and drop goals (1 point), all of which involve kicking the ball between
the posts and over the crossbar.
Rugby league is known for its physicality and fast pace, with players engaging in tackles and
collisions to gain possession of the ball, defend their try line, and make progress towards the
opponent’s try line. Due to its high-velocity contact, cardio-based endurance and minimal use
of body protection, rugby league is widely regarded as one of the toughest and most brutal
collision sports in the world (Siddell, 2011). As such, understanding the physiological demands
of rugby league matchplay is crucial in tailoring training routines and improving performance.

Rugby league is played around the world, with 51 nations having officially registered men’s
national teams (International Rugby League, 2023), although only 4 countries (Australia, England, France, and New Zealand) have teams that play at the professional level. This study
uses data from the Super League competition, England’s first division of rugby league and the
second-largest rugby league competition globally after Australia’s National Rugby League.
1.3 Objectives of Research
The main objective of this project is to develop position-specific activity profiles for rugby league
players based on the distributions of behavioural states generated from the HMM models of
player movement. The resultant activity profiles will then be compared with the aim of finding
unique characteristics between positions. We aim to demonstrate the usefulness of HMMs as
a novel method of analyzing rugby league player tracking data with the hope it will lead to
further research that applies HMMs to human movement.
1.4 Scope of Research
This research project will be limited to the application of HMMs to rugby league player movement data, and discussion of the results thereof. The aim of this research is to uncover differences between positions, so variation between individuals with the same playing position is not
considered.
We have access to only Super League data, so this research may not be applicable to National
Rugby League matchplay since there are several key distinctions between the 2 leagues (Woods
et al., 2018). Additionally, the data does not indicate which team has possession of the ball
at any given moment, so our research is unable to investigate the differences between the
physiological demands of players during attack and defence. Extensions of this research may
attempt to model attacking movement compared to defensive movement since the existing
literature indicates that defending is significantly more physically taxing than attacking (Sykes
et al., 2009; Gabbett et al., 2014).
In terms of model implementation, this research will explore models with differing numbers of
underlying states. However, due to computing constraints, we will not build models with more
than 5 states. Further research could delve into more detail and include models with more
states since existing literature groups movement into up to 8 categories (Sirotic et al., 2011).
1.5 Structure of Dissertation
Section 2 of this project gives an outline of the existing research on both HMMs and activity
profiling. The theoretical framework of HMMs as well as their range of application to animal
telemetry data is discussed in detail. After that, the history of activity profiling in competitive
sports, with particular emphasis on rugby league, is explored, noting the progression in research
from time-motion analysis to microtechnology. Lastly, the overlap between activity profiling
and rugby league is briefly discussed, although no literature that merges these two concepts
currently exists.
Section 3 gives a thorough overview and description of the data, including the methods used to
clean the data and remove data errors. This section explores the data in great detail, providing

information about the univariate differences between the activity profiles of different groups as
well as the distributions of several key metrics.
Section 4 describes the approach we took to model-building, as well as an overview of how
HMMs and the related algorithms work. The key components of model-building involve the
number of states to be specified, determining a tradeoff between computational constraints
and model accuracy, selection of data emission streams and distributions, and incorporating
covariates, all of which are detailed in this section.
Results are then presented in section 5, along with a discussion of the notable findings. Of
primary interest are the state-dependent data emission stream distributions, as they form the
position-specific activity profiles. Significant differences between positions are analysed and
explained based on the roles associated with each position in rugby league. Since 2 models
were built, the results from each model are interpreted individually before being compared to
each other. The limitations and possible extensions of this study are also outlined. Finally,
section 6 provides a summary of our findings.
