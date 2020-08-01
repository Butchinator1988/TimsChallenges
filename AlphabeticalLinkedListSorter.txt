package com.company;

import java.util.Iterator;
import java.util.LinkedList;
import java.util.ListIterator;
import java.util.Scanner;

public class IterateLinkedListAlphabetically {
        public static void main(String[] args) {
                LinkedList<String> placesToVisit = new LinkedList<String>();

                addInOrder(placesToVisit, "Amsterdam");//examples
                addInOrder(placesToVisit, "Denmark");
                addInOrder(placesToVisit, "Uruguay");
                addInOrder(placesToVisit, "Belgium");
                addInOrder(placesToVisit, "Dubai");
                addInOrder(placesToVisit, "America");
                addInOrder(placesToVisit, "America");

                printList(placesToVisit);
                System.out.println(placesToVisit.size());

        }

        private static void printList(LinkedList<String> linkedList) {
                Iterator<String> i = linkedList.iterator();
                while (i.hasNext())
                {
                        System.out.println("Visiting " + i.next());
                }
                System.out.println("The end");
        }

        private static boolean addInOrder(LinkedList<String> linkedList, String newCity)
        {
                ListIterator<String>stringListIterator = linkedList.listIterator();     //initializes the ListIterator to run through the LinkedList

                while (stringListIterator.hasNext()) {                                  //while the newly created list has a next index, continue
                        int comparison = stringListIterator.next().compareTo(newCity);  //compares the numerical value returned from next() and newCity. Whichever one is higher is valued 1 the other 0.
                        if (comparison == 0)                                            //if the two inputs compared = 0 then the inputs are identical.
                        {
                                System.out.println(newCity + " is already in the list");
                                return false;
                        } else if (comparison > 0) {
                                stringListIterator.previous();
                                stringListIterator.add(newCity);
                                return true;
                        } else if (comparison < 0) {
                                //move onto next city
                        }
                }
                stringListIterator.add(newCity);
                return true;
        }
        private static void visit (LinkedList cities)
        {
                Scanner scanner = new Scanner(System.in);
                boolean quit = false;

                ListIterator<String>listIterator = cities.listIterator();
        }
}
