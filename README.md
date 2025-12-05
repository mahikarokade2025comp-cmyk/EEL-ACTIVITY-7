# EEL-ACTIVITY-7
#include <stdio.h>

struct Song {
    char name[50];
    struct Song *next;
};

void play(struct Song *s) {
    if (s == NULL) {
        printf("\nEnd of Playlist.\n");
        return;
    }

    printf("Now Playing: %s\n", s->name);

    play(s->next);
}

int main() {
    struct Song s1 = {"Shape of You", NULL};
    struct Song s2 = {"Perfect", NULL};
    struct Song s3 = {"Believer", NULL};

    s1.next = &s2;
    s2.next = &s3;

    play(&s1);

    return 0;
}
