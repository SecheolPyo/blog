---
layout: default
title: Tree
parent: C Programming
nav_order: 1
---

# Tree
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---

## Binary Tree General

이진 트리에서의 최대 깊이

/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     struct TreeNode *left;
 *     struct TreeNode *right;
 * };
 */

int isMaxDepth(struct TreeNode* root, int n) {
    int left = 0, right = 0, max = 0;
    if (root->left==NULL && root->right==NULL) max = n+1;
    else {
        if (root->left) left = isMaxDepth(root->left, n+1);
        if (root->right) right = isMaxDepth(root->right, n+1);
        
        if (left > right) max = left;
        else max=right;
    }
    return max;
}

int maxDepth(struct TreeNode* root){

    int n=0;
    if (root==NULL) return 0;
    return isMaxDepth(root, n);
    
}