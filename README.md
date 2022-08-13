# Enterprise survey and analysis of NYC mental health clinic wait times

### M.S. Data Journalism Master's Project 2022

Early this year I found myself searching for somewhat urgent mental health care for
my six-year-old son. It was extremely challenging to figure out who was a qualified
provider, let alone if they would be available or take his insurance. I called a couple
of well-regarded hospitals, and that is when I first heard clinics saying they weren’t
taking any new patients or had several-months-long waitlists.

This experience made me wonder if I could do something to quantify how
accessible mental health care was for the more than one million children who are
on Medicaid in New York City.

I called 172 outpatient mental health clinics asking whether they were accepting new child patients and how long the wait time was for a new patient appointment, and these notebooks were attempts to analyze and visualize the results.

#### Methodology
##### SURVEY
Looking for a universe of clinics, I chose to survey Article 31 community
clinics at the advice of Alice Bufkin. As Bufkin says, they are the most common
outpatient setting for mental health, and most locations work with Medicaid.

After receiving a list of all child and adolescent Article 31 clinics from the Office of Mental Health, I used Regex for common phrases that indicated the location was a
school clinic (ie yeshiva, school, P.S., I.S., etc) and labeled thosed as such.
Calls: The bulk of the surveying was conducted in July. Before receiving the list
from the state, I had called some hospital outpatient clinics in June. I went through
the list in no particular order, searching for a main clinic phone number on Google. I
called the clinics, and if someone answered, I did not identify myself as a journalist,
unless I was specifically asked where I was calling from. I simply asked:

1. If they were accepting new child patients
2. How long was the wait time for a new patient appointment.

When it became clear that many clinics have a wait time for intake and then a
subsequent wait time to be seen by a therapist, I began asking for the wait time for
a new patient appointment with a therapist.

If clinic representatives asked how old the child was, I gave a number between
6-8. This at first was unintentional. I have a 6-year-old. However, I continued with
this strategy for consistency's sake, when I realized I was introducing a bias into
the survey. If a clinic was labeled an adolescent only clinic, I changed the wording
to “teenage” patients, and gave the age of 16 if asked.

I aimed to get 75% of clinics in each of the boroughs and met this goal, however, I
struggled to get in contact with clinics in East Harlem and the Upper East Side, as
well as many NYC Health and Hospitals locations.

Data Entry: More often than not, representatives gave a range. “Four to six weeks,”
or “two to four months.” For each clinic I entered a “weeks_low” and a “weeks_high”
and took the average of the two numbers. If one figure was given, like “three
weeks,” I put that in both columns. To calculate weeks out of month figures, I
multiplied the number of months by 4.345, a standard number of weeks in a
month.

If a clinic mentioned intake, I would make sure I get the estimate of how long to see
a therapist in person. The calculation would be the amount of time to wait for an
intake appointment plus the time until a therapist could be seen.

Clinics often used time references like, “end of the month,” or a specific date. I
would calculate the number of weeks from the time I reached them to that date.
Unfortunately, I logged the day I called them, but did not keep complete track of
the date that a clinic was reached if I received a call back.
Many clinics would also use “or more” in their estimates. “Two months or more.” I
entered the first number as the “weeks_low” and added two weeks for the “or
more.”

If a clinic said they were not working with children under 18, but were on the state’s
list of child and adolescent clinics, then I would label them as “nokids_notherapy.”
If a clinic said they did not offer mental health or individual therapy, I also gave it
this label.

##### PSYCHOLOGY TODAY

Using Beautiful Soup, I scraped 5,000 therapist profiles from Psychology Today. I
filtered the ages served to be 6-10, and 14-18. I would have done 11-13 if I had had
more time, but decided 5,000 was a sufficient sample.

I created a new set of searches for each county and scraped the results. Using
Regex, I parsed the “Cost per Session” portion of the profile and extracted a
number. Figures were formatted as either a range (150-200), a floor (80+), a
limit (Up to 350) or a single number (220).

I averaged ranges, and then took a median of all of the entries, not making any
adjustments for the floors or the ceilings. This tactic proved safe as the median
figure (180) remained virtually unchanged (175) even when I removed the floors
and limits.

I filtered out one profile, an outlier, that listed a range of 4500-6500, because
they were specifically focusing on comprehensive evaluations, which are much
more lengthy and involved than a single session of therapy. I did not apply this
level of scrutiny to the rest of the listings.


```python

```
